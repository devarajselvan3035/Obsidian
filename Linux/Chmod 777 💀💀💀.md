
# understanding chmod 777

[#scor32k](https://dev.to/t/scor32k)[#linux](https://dev.to/t/linux)[#ubuntu](https://dev.to/t/ubuntu)[#beginners](https://dev.to/t/beginners)

### [](https://dev.to/scorcism/understanding-chmod-777-3pm4#understanding-raw-chmod-777-endraw-)Understanding `chmod 777` ❓

> NOTE: The is a contains small portion of [Linux file permission](https://dev.to/scorcism/file-permission-2d8) blog. Contents from the parent blog are pruned and customize for this article. Thank you for reading.

In Linux, **permissions** define the access rights for three categories of users: 👤User, 👥Group, and Others.

- The **User** is the file or directory owner.
- The **Group** consists of users belonging to the same group as the owner.
- **Others** refers to the general public.

Each of these users can have three types of permissions: 📕Read, ✍️Write, and Execute🥬.

- **Read ( r )**: Allows viewing the content of the file. Represented by an octal value of `4`.
- **Write ( w )**: Allows modifying or editing the file. Represented by an octal value of `2`.
- **Execute ( x )**: Allows running the file (if it's a script) or traversing a directory. Represented by an octal value of `1`.

These permissions are presented as a string of nine characters for each file or directory:

Example:  

```
rw-r--r--
```

- `rw-` means the owner has **read** and **write** permissions.
- `r--` means the group has **read-only** permissions.
- `r--` means others have **read-only** permissions.

---

### [](https://dev.to/scorcism/understanding-chmod-777-3pm4#octal-mode-in-raw-chmod-endraw-)Octal Mode in `chmod`

In advanced file permission manipulation, **numeric values** are used to represent permissions:

- **Read ( r )** = `4`
- **Write ( w )** = `2`
- **Execute ( x )** = `1`

To set permissions using octal values, you assign a three-digit number representing the permissions for **User**, **Group**, and **Others**. For example, `777` gives read, write, and execute permissions to everyone.

> **Note:** The maximum permission `777` means **User**, **Group**, and **Others** all have full **read**, **write**, and **execute** permissions. However, granting such permissions can pose a security risk.

---

### [](https://dev.to/scorcism/understanding-chmod-777-3pm4#example-modifying-file-permissions-with-octal-values)Example: Modifying File Permissions with Octal Values

Let’s say we want to set specific permissions:

- **User**: Read (`4`) and Execute (`1`) ⇒ `4 + 1 = 5`
- **Group**: Read-only (`4`)
- **Others**: Read-only (`4`)

The combined permission value is `544`, meaning the user can read and execute, and both the group and others can only read.  

```
chmod 544 myfile.txt
```

[![https://imgur.com/H2DPPRF.png](https://media.dev.to/cdn-cgi/image/width=800%2Cheight=%2Cfit=scale-down%2Cgravity=auto%2Cformat=auto/https%3A%2F%2Fdev-to-uploads.s3.amazonaws.com%2Fuploads%2Farticles%2Fmitbhgilipl0u4k1i5hl.png)](https://media.dev.to/cdn-cgi/image/width=800%2Cheight=%2Cfit=scale-down%2Cgravity=auto%2Cformat=auto/https%3A%2F%2Fdev-to-uploads.s3.amazonaws.com%2Fuploads%2Farticles%2Fmitbhgilipl0u4k1i5hl.png)

This sets the permission to `r-xr--r--`, which breaks down into three blocks:

- `r-x` for the **User**
- `r--` for the **Group**
- `r--` for **Others**

> **Note:** The `-` before the permissions indicates the file type, where `-` is for regular files and `d` is for directories.

---

### [](https://dev.to/scorcism/understanding-chmod-777-3pm4#example-2-complex-permission-setup)Example 2: Complex Permission Setup

Let’s give the following permissions:

- **User**: Read (`4`) and Write (`2`) ⇒ `4 + 2 = 6`
- **Group**: Write (`2`) and Execute (`1`) ⇒ `2 + 1 = 3`
- **Others**: Read (`4`)

The combined value is `634`, meaning:  

```
chmod 634 myfile.txt
```

---

### [](https://dev.to/scorcism/understanding-chmod-777-3pm4#changing-file-ownership)Changing File Ownership

To change the ownership of a file or directory, use the `chown` command:  

```
chown username myfile.txt
```

> Note: You might require root privileges for this command.

---

### [](https://dev.to/scorcism/understanding-chmod-777-3pm4#changing-file-group-ownership)Changing File Group Ownership

To change the group ownership of a file, use the `chgrp` command:  

```
chgrp groupname myfile.txt
```

---

### [](https://dev.to/scorcism/understanding-chmod-777-3pm4#important-tips)Important Tips

- **Avoid using `777`**: It’s a significant security risk.
- Use `ls -l` to display detailed file information, including permissions.
- Don’t forget about `umask`[_](https://dev.to/scorcism/file-permission-2d8), which affects default file permissions.