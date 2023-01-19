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

Extracting a tarball does **not** empty the tarball. You can extract from a tarball as many times as you want without affecting the tarball's content.  

## 2.0 Compressing Tarballs
The main types of compression algorthims are `gzip` and `bzip2`. The `gzip` compression algorithm tends to be faster thean `bzip2`, but `gzip` usally offers less compression.

### 2.1 Using gzip
Compressing with gzip:
```
gzip <name of tarball>
```
Decompressing with gzip:
```
gunzip <name of tarball>
```
When compressing with gzip, the file extension `.gz` is automatically added to the `.tar` archive, thus the compressed archive would have the file extension `.tar.gz`.

### 2.2 Using bzip2
Compressing with gzip:
```
bzip2 <name of tarball>
```
Decompressing with gzip:
```
bunzip2 <name of tarball>
```
When compressing with bzip2, the file extension `.bz2` is automatically added to the `.tar` archive, thus the compressed archive would have the file extension `.tar.bz2`.

## 3.0 Using tar to archive and compress
Creating a tarball and compressing via gzip:
```
tar -cvzf <name of tarball> <file>...
```
Decompressing a tarball and extrating via gzip:
```
tar -xvzf <name of tarball> 
```

For `bzip2` use the `j` options. For `xzip` us the `J` option.  

## 4.0 Creating .zip files
Creating a .zip archive:
```
.zip <name of zipfile> <file>...
```
Extrating a .zip archive:
```
unzip <name of zipfile> 
```

