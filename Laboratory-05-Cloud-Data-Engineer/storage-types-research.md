# Cloud Storage Types Research

| Storage Type | Description | Primary Use Case | Cloud Provider Example |
|---|---|---|---|
| Block Storage | Splits data into fixed-size blocks, each with its own unique ID, and presents them to a VM as a raw, unformatted volume. The operating system is responsible for formatting it and managing the file system. | Boot volumes and high-performance workloads, such as transactional databases that need fast, low-latency reads and writes | Amazon EBS, Azure Disk Storage, Google Persistent Disk |
| File Storage | Keeps data as files organized in a hierarchy of folders, and makes them available over the network through protocols such as NFS or SMB. | Shared directories that many VMs or users access at once, such as legacy enterprise apps that rely on a shared network drive | Amazon EFS, Azure Files, Google Cloud Filestore |
| Object Storage | Places data in a flat, highly scalable "bucket," where each object is packaged with its metadata and a unique Object ID, and is reached through HTTP/HTTPS and REST APIs (such as S3). | Holding huge volumes of unstructured data, including website images, streaming media, backups, and archives | Amazon S3, Azure Blob Storage, Google Cloud Storage |

## Why Object Storage Is the Best Fit for the Client's Photos

For a photo-sharing application that will receive millions of user-uploaded images, Object Storage is the obvious pick. It has no need for complex folder structures or file locking, so it can grow to petabytes of unstructured data such as photos with little effort. Block storage, by contrast, is designed for fast, structured data tied to a single attached volume. Object storage can also be reached directly over HTTP/HTTPS through simple APIs, which makes it easy to connect to a web application. On top of that, it costs much less for storing large amounts of files that rarely change, like photos.
