# Linux File Archiving and Compression Notes
## Overall Process
1. `Create a Tarball`  
First, creat a tar file pr "`tarball`". A tarball is a way of bundling together the files that you want to archive.
2. `Compress the tarball` with a compression algorithm  
Secondly, compress the tarball with a compression algorithm; leaving a compressed archive.

## 1.0 Creating a Tarball
Tarballs are created using the `tar` command.
```
tar -cvf <name of tarball> <file>...
```
`The -c option`: "create". This allows you to create a tarball. [required]  
`The -v option`: "verbose". This makes tar give feeback on the process. [optional]  
`The -f option`: Tells tar that the next arument is the name of the tarball. [required]  
`<name of tarball>`: The absolute or relavitve file path to where you want the tarball to be placed; e.g. ~/Desktop/myarchive.tar. Always add .tar to the filename for clarity.   
`<file>`: The absolute or relative file paths to files that you want to insert into the tarball. You can have as many as you like and wildcards are accepted.  
### 1.1 Checking Tarball's Contents
```
tar -tf <name of tarball>
```
`The -t option`: "test-label". This allows you to check the contents of a tarball. [required]   


### 1.2 Extracting From a Tarball
```
tar -xvf <name of tarball>
```
`The -x option`: "extract". This allows you to extract a tarball's contents. [required]  

Extract