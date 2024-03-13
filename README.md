# Hey! I'm Filing Here

In this lab, I successfully implemented the following 1 MiB ext2 file system with 2 directories, 1 regular file, and 1 symbolic link. I established the directory structure by creating two directories: one named root and the other lost+found. Moreover, I added a regular file called hello-world and a symbolic link named hello (which points to hello-world), ensuring they were properly linked within the directory structure. 

## Building
Build the program by running:
```make```

## Running
Run the executable to create cs111-base.img:
```./ext2-create``` 
Dump the filesystem information to help debug:
```dumpe2fs cs111-base.img```
Check that the filesystem is correct:
```fsck.ext2 cs111-base.img```
Create a directory to mount your filesystem to:
```mkdir mnt```
Mount your filesystem (loop lets you use a file):
```sudo mount -o loop cs111 -base.img mnt```

## Cleaning up
Unmount the filesystem:
```sudo umount mnt```
Delete the directory used for mounting:
```rmdir mnt```
Clean up all binary files by running:
```make clean```
