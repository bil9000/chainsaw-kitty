# some useful commands

I just needed a place to put these so I could find them.

This is to flatten a a hierarchical directoruy structure

``` find .  -type f -print0 | xargs -0 -I%%% cp %%% flat 

find Attachments/ -mindepth 2 -type f -exec mv  '{}'Attachments/ ';' 


```

This command grabs tehe InstanceID, Instance Name, PriavteIP and VPC

```
aws ec2 describe-instances \
    --filters Name=tag-key,Values=Name \
    --query 'Reservations[*].Instances[*].{Instance:InstanceId,Vpc:VpcId,PrivateIP:PrivateIpAddress,Name:Tags[?Key==`Name`]|[0].Value}' --output table >> instances.tsv
