[Main Page](https://github.com/davidj778/davidj778)

# Use Linux commands to manage file permissions

Scenario

Review the scenario below. Then, complete the step-by-step instructions.

You are a security professional at a large organization. You mainly work with their research team. Part of your job is to ensure users on this team are authorized with the appropriate permissions. This helps keep the system secure.

Your task is to examine existing permissions on the file system. You’ll need to determine if the permissions match the authorization that should be given. If they do not match, you’ll need to modify the permissions to authorize the appropriate users and remove any unauthorized access.



# File permissions in Linux

## Project description
[Describe what you accomplish through Linux commands.]

## Check file and directory details

To find the current file permissions, use the Linux command: 

```
ls -l
```
The /home/researcher2/projects directory would look like the following:

```
project_k.txt
   User = read, write,
   Group = read, write
   Other = read, write
project_m.txt
   User = read, write
   Group = read
   Other = none
project_r.txt
   User= read, write
   Group = read, write
   Other = read
project_t.txt
   User = read, write
   Group = read, write
   Other = read
.project_x.txt
   User = read, write
   Group = write
   Other = none
```

## Describe the permissions string

The permissions string for project_m.txt would be:

```
-rw-r——-
```

The “r” stands for read, the “w” stands for write and the “-“ stands for none. The “-“ for the first character does not mean “none”, it means that it’s a regular file.


## Change file permissions
[Add content here.]
## Change file permissions on a hidden file
[Add content here.]
## Change directory permissions
[Add content here.]
## Summary
[Add content here.]

