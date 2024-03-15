# Hey! I'm Filing Here

In this lab, I successfully implemented the following 1 MiB ext2 file system with 2 directories, 1 regular file, and 1 symbolic link. This file system contains a superblock, group descriptor, block bitmap, inode bitmap, and inode table. I established the directory structure by creating two directories: one named root and the other named lost+found. Moreover, I added a regular file called hello-world and a symbolic link named hello (which points to hello-world), ensuring they were properly linked within the directory structure. 

## Building
Build the program by running:  
```shell 
make
```

## Running
Run the executable to create cs111-base.img:  
```shell
./ext2-create
```  
Optional: Dump the filesystem information to help debug:  
```shell 
dumpe2fs cs111-base.img
```  
Check that the filesystem is correct:  
```shell 
fsck.ext2 cs111-base.img
```  
Create a directory to mount your filesystem to:  
```shell 
mkdir mnt
```  
Mount your filesystem (loop lets you use a file):  
```shell 
sudo mount -o loop cs111-base.img mnt
```  
Now you can use the filesystem, for example by running:
```shell
ls -ain mnt/```

## Cleaning up
Unmount the filesystem:  
```shell 
sudo umount mnt
```  
Delete the directory used for mounting:  
```shell
rmdir mnt
```  
Clean up all binary files by running:  
```shell
make clean
```  
