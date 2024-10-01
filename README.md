# Cheat Sheet - ASM x86-64 General

### SYS_OPEN RSI FLAGS

| FLAG           | HEX             | DECIMAL    | BINARY                 | Description                                                    |
| -------------- | --------------- | ---------- | ---------------------- | -------------------------------------------------------------- |
| O_RDONLY       | 0x0             | 0          | 0b0000                 | Open for reading only                                          |
| O_WRONLY       | 0x1             | 1          | 0b0001                 | Open for writing only                                          |
| O_RDWR         | 0x2             | 2          | 0b0010                 | Open for reading and writing                                   |
| O_CREAT        | 0x40            | 64         | 0b0100000              | Create file if it does not exist                               |
| O_EXCL         | 0x80            | 128        | 0b10000000             | Ensure that this call creates the file                         |
| O_TRUNC        | 0x200           | 512        | 0b1000000000           | Truncate the file to zero length                               |
| O_APPEND       | 0x400           | 1024       | 0b10000000000          | Write operations will append to the end of the file            |
| O_NONBLOCK     | 0x800           | 2048       | 0b100000000000         | Open in non-blocking mode                                      |
| O_DSYNC        | 0x1000          | 4096       | 0b1000000000000        | Write operations will complete when data is physically written |
| O_RSYNC        | 0x2000          | 8192       | 0b10000000000000       | Read operations will complete when data is physically written  |
| O_SYNC         | 0x4000          | 16384      | 0b100000000000000      | Write operations will complete when data is written            |
| O_DIRECTORY    | 0x10000         | 65536      | 0b1000000000000000     | Fail if the file is not a directory                            |
| O_NOFOLLOW     | 0x20000         | 131072     | 0b10000000000000000    | Do not follow symbolic links                                   |
| O_CLOEXEC      | 0x40000         | 262144     | 0b100000000000000000   | Set the close-on-exec flag for the new file descriptor         |
| O_TMPFILE      | 0x200000        | 2097152    | 0b10000000000000000000 | Create an unnamed temporary file                               |

### SYS_OPEN RDX PERMISSION MODES

| PERMISSION     | OCTAL           | HEX        | DECIMAL   | Description                         |
| -------------- | --------------- | ---------- | --------- | ----------------------------------- |
| S_IRUSR        | 0o400           | 0x100      | 256       | Read permission for owner           |
| S_IWUSR        | 0o200           | 0x80       | 128       | Write permission for owner          |
| S_IXUSR        | 0o100           | 0x40       | 64        | Execute permission for owner        |
| S_IRGRP        | 0o40            | 0x20       | 32        | Read permission for group           |
| S_IWGRP        | 0o20            | 0x10       | 16        | Write permission for group          |
| S_IXGRP        | 0o10            | 0x8        | 8         | Execute permission for group        |
| S_IROTH        | 0o4             | 0x4        | 4         | Read permission for others          |
| S_IWOTH        | 0o2             | 0x2        | 2         | Write permission for others         |
| S_IXOTH        | 0o1             | 0x1        | 1         | Execute permission for others       |

### ERROR CODES FOR SYS_OPEN, SYS_READ, SYS_WRITE, ETC.

| E-CODE       | HEX-VALUE       | DEC-VALUE  | Description                       |
| ------------ | --------------- | ---------- | --------------------------------- |
| EACCES       | 0x0000000D      | 13         | Permission denied                 |
| EEXIST       | 0x0000000B      | 11         | File exists                       |
| EFAULT       | 0x0000000E      | 14         | Bad address                       |
| EINVAL       | 0x00000016      | 22         | Invalid argument                  |
| ENOENT       | 0x00000002      | 2          | No such file or directory         |
| ENOSPC       | 0x00000028      | 28         | No space left on device           |
| ENOTDIR      | 0x00000020      | 20         | Not a directory                   |
| EISDIR       | 0x00000015      | 21         | Is a directory                    |
| EMFILE       | 0x00000018      | 24         | Too many open files               |
| ENFILE       | 0x0000001E      | 27         | Too many open files in system     |
| EROFS        | 0x0000001C      | 30         | Read-only file system             |
| ENOTEMPTY    | 0x00000027      | 39         | Directory not empty               |
| ELOOP        | 0x00000028      | 40         | Too many levels of symbolic links |
| ENAMETOOLONG | 0x0000003B      | 36         | File name too long                |
