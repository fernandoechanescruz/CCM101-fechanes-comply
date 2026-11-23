# Reflection

### 1. Why is object storage better suited for storing millions of photos compared to a traditional block storage hard drive?
Block storage works like a raw hard drive attached to a single VM. It is excellent for fast, structured reads and writes, but it struggles to scale to huge volumes of unstructured files. Object storage keeps data in a flat, virtually unlimited bucket, where each file is an object with its own ID and metadata and there are no folders to maintain. This suits millions of photos well, since they only need to be saved and retrieved by ID instead of being arranged in a traditional file system.

### 2. How did using Docker make it easier to deploy the MinIO storage server?
Rather than installing MinIO by hand, sorting out its dependencies, and configuring the networking myself, I used Docker to get a fully working object storage server running from one command. The `-e` flags took care of configuration by setting the admin credentials, and `-p` exposed the necessary ports. Everything came packaged in a single reusable, disposable container.

### 3. What is a "bucket" in the context of cloud storage?
A bucket is the top-level container in object storage that holds files, which are called "objects." Unlike folders in a traditional file system, buckets do not branch into deep hierarchies. Objects sit in a flat structure inside the bucket, and each is identified by a unique Object ID instead of a file path.

### 4. How do you think large enterprise companies ensure their object storage data is not lost if the physical server crashes?
It mostly comes down to replication, which means constantly copying data across multiple physical drives, server racks, or even separate geographic regions so that one hardware failure does not cause data loss. Companies also add backups on top of replication, often following the 3-2-1 backup rule, because replication alone would copy a corrupted or accidentally deleted file as well.

### 5. How is your confidence in navigating the Linux command line growing?
After five labs, using the terminal to run Docker commands and manage containers feels far more natural than it did in Lab 1, when I was still learning basics like `ls` and `cd`. Launching a working server with a single command still feels a bit surreal, but it is making the terminal less intimidating and turning it into just another tool.

