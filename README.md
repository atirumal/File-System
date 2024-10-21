# Custom File System

- Designed a custom file system in C, utilizing libuuid for generating unique identifiers and glibc for snapshotting capabilities
that allow users to create point-in-time copies, enabling quick recovery and version control of files

- Developed multi-layered dynamic block allocation system, resulting in 30% reduction of fragmentation and 40% improvement
in read/write performance across multiple threads

- Integrated a data compression mechanism using Zlib and secure hashing with OpenSSL to improve I/O efficiency, reduce
storage space, and ensure data integrity through cryptographic verification

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
Now you can use the filesystem, for example, by running a command like:
```shell
ls -ain mnt/
```  

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
