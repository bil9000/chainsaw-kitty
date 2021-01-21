# some useful commands

I just needed a place to put these so I could find them.

This is to flatten a a hierarchical directoruy structure

``` find .  -type f -print0 | xargs -0 -I%%% cp %%% flat 

