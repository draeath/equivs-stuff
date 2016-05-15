Please see [LICENSE.md](./LICENSE.md) for license information.  

Long story short, debian (and derivatives) have a neat tool called "equivs"
that allows one to build empty packages that have package metadata.  

This can be quite useful, but also incredibly dangerous. [Do not take this
tool lightly.](https://www.debian.org/doc/manuals/apt-howto/ch-helpers.en.html#s-equivs)

In this case, I find myself often going "what was $MAINTAINER thinking? why
on Earth does this top level metapackage 'foo' depend on 'bar?" If one were
to remove the 'bar' package, 'foo' will get pulled out with it, causing nigh
untold amounts of hilarity when 'apt-get autoremove' rolls around. Potentially
you would also miss out on any other packages that are later added to the
top level metapackage 'foo'  

Case in point: `anti-cheese`  

Don't get be wrong - I have nothing against the "cheese" package (meant to take
selfies for profile photos and the like with a webcam?) but this bit of
software has *absolutely no place* in environments outside of an end-user's
desktop - for example, in a VM that would never even see a webcam.  

This repository is just something I created to keep track of the various equivs
control files I've written when dealing with my own systems. They may not work
for you. They may cause your system to explode. Use with care. Also, I'm happy
to take any others, if this repository should ever be of use to anyone else!  

NOTE: Because these are dummy packages and they should *never* be distributed
to end-users (they're welcome to come get them of course), the maintainer info,
descriptive text, and so on isn't really filled out legitimately.  
