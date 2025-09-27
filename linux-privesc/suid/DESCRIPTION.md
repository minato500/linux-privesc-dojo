Non-root and non-sudo users need elevated privileges to perform certain tasks, but administrators cannot constantly share the root password or grant permanent sudo access. In such cases, the administrator can set the Set User ID (SUID) permission bit on a program. This allows a user to execute the program with the privileges of the program's owner (often root) without needing the owner’s password.

```
hacker@meowsec:~$ ls -la /usr/bin/cat
-rwsr-xr-x 1 root root 25756 Jun  4 20:44 /usr/bin/cat
hacker@meowsec:~$
```

The s part in place of the executable bit means that the program is executable with SUID. It means that, regardless of what user runs the program (as long as they have executable permissions), the program will execute as the owner user (in this case, the root user)

Note: Only the hacker home directory is writable
