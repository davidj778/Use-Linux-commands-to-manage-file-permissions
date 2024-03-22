[Main Page](https://github.com/davidj778/davidj778)

# Use Linux commands to manage file permissions

Scenario

Review the scenario below. Then, complete the step-by-step instructions.

You are a security professional at a large organization. You mainly work with their research team. Part of your job is to ensure users on this team are authorized with the appropriate permissions. This helps keep the system secure.

Your task is to examine existing permissions on the file system. You’ll need to determine if the permissions match the authorization that should be given. If they do not match, you’ll need to modify the permissions to authorize the appropriate users and remove any unauthorized access.



# File permissions in Linux

## Project description

An organization wants to configure the permissions for a few files. They need the security analyst to check the permissions and update them if needed.

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
   User = read, write
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

The organization does not allow other to have write access to any files.

```
chmod o-w project_k.txt
```

The above command will change the permissions of other to write only. “chmod” stands for change mode, which is the command that changes the permissions for the file. The o in o-w stands for “other” and the w stands for write. After the change is made, you can use “ls -la” to see the new update.

## Change file permissions on a hidden file

The organization does not want the archived .project_x.txt to have write permissions for anyone. Instead, they want the user and group to be able to read the file. 

    .project_x.txt
        User = read, write
        Group = write
        Other = none

In order to update this file with the proper permissions, you would use the following:

```
chmod u-w, g-w, g+r .project_x.txt
```

- u-w takes away the write permission from users.

- g-w takes away the write permission from group.

- g+r adds the read permission to group


## Change directory permissions

The organization only wants researcher2 to have access to the drafts directory and its contents.

Here are the permissions for the subdirectory file drafts:

```
User = read, write, execute
Group = execute
Other = none
```

To accomplish this task, you use the following command to remove the execute permission for everyone except the user of the file.

```
chmod g-x drafts
```

## Summary

After reviewing all the permissions, it was found that multiple files needed their permissions changed. By using the “chmod” command followed by certain instructions(u-w, g+r, as some examples), permissions were either added or taken away.

