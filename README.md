#JENKINS AND AWS STEPS

## JENKINS

## what is CI CD?
continuous integration and continuous deployment

## what is an automation server?
provisioned bash script that opens automatically

## why do we restrict build and how?

# AWS

### Setting up an EC2 server:

AMI - choose a server which is familar to you (for example ubuntu18.04).

Instance - t2.micro

Configure Instance - Network - DevOpsStudent - Subnet - DevOpsStudentSubnet and also make sure enabled.

Add Storage - not necessary for now but can be adjusted dependant of requirements.

Add Tags - {"Name", "zack-eng54-first-ec2"} {"Cohort", "Eng54"} (ensure that Name is capitalised and that you stick to good naming convention).

Connect to ports: 80, 22, 8080, 443, 3000 and set the ip to "my IP".

Create a key and save it to the .ssh folder on your machine. This can be done by downloading the zip on AWS and then moving it into your .ssh folder. To move files into another directory you can use.

This can be done by using the mv command.

```mv /home/zack/testfile /home/zack/testfile2```

### some mv commands
```
mv -f	force move by overwriting destination file without prompt
mv -i	interactive prompt before overwrite
mv -u	update - move when source is newer than destination
mv -v	verbose - print source and destination files
man mv	help manual
```

## Use this command to get into the ssh
```ssh -i <location of .pem> ubuntu@<ip>```
**example:**
```ssh -i ~/.ssh/zack-eng54.pem ubuntu@ <IP ADDRESS>```

## Give read permissions to the user for the key
 ```chmod 400 zack-eng54.pem```

## Give execution rights to the user for the provision.sh file
 ```chmod +x provision.sh```

## Upload the file yourFile.xyz to your home directory on the VM
 scp -i path/to/key file/to/copy <user>@ec2-xx-xx-xxx-xxx:path/to/file **example:**```scp -i ~/.ssh/zack-eng54.pem environment/app/provision.sh ubuntu@3.249.10.187:/home/ubuntu```

## Upload the folder to your home directory on the VM
- scp(secure copy)
 ```scp -r -i ~/.ssh/zack-eng54.pem environment/app/provision.sh ubuntu@3.249.10.187:/home/ubuntu```

## Rsync (Remote Sync)
- is a most commonly used command for copying and synchronizing files and directories remotely as well as locally in Linux/Unix systems.
```rsync <dir1/ dir2>```
