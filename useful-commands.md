# Some Useful Commands

I just needed a place to put these so I could find them.  They may be a bit Mac Heavy but hey! So what!

## Flatten Hierarchical Directory Structure
If you have a bunch of files nested in folder from here to eternity, a la *matroshka* --these are a couple of commands to pull the contents out.
``` 
find .  -type f -print0 | xargs -0 -I%%% cp %%% flat 
```
or this one seems to work better:
```
find Attachments/ -mindepth 2 -type f -exec mv  '{}'ttachments/ ';'
```


