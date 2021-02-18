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
## Recursivley Lock Or Unlock Files and Folders 

I have liberated this next copy and paste from [tinyapps.org](https://tinyapps.org/blog/200912130700_lock_unlock_files_recursively_os_x.html) oh, who had in turn liberated it from someobdy else. ButI'm going back after one query, if you want to dig down into the origin story of the the locking or unlocking scripts, there is only so much I can do for you.  Fly away and be free!

uchg is to lock the folder (think unchanged) 
nouchg is the oppostie (no think unchanged)
```
chflags -R uchg directory

chflags -R nouchg directory
```



```

This command grabs tehe InstanceID, Instance Name, PriavteIP and VPC

```
aws ec2 describe-instances \
    --filters Name=tag-key,Values=Name \
    --query 'Reservations[*].Instances[*].{Instance:InstanceId,Vpc:VpcId,PrivateIP:PrivateIpAddress,Name:Tags[?Key==`Name`]|[0].Value}' --output table >> instances.tsv


