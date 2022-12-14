- [[S3|simple storage service]]
- secure durable highly scalable object storage
- store and retreive any amount of data at low cost
- simple to use
- manage data as objects instead of file systems or blocks
    - store files
    - any file type
    - cannot run an operating system or databases
    - just a place to store static files
- number of objects is unlimited
- object can be up to 5TB
    - chunking/partitioning (parquet, etc.) can get around this limit but is not done by [[S3]]
- store files in buckets (folder)
- globally unique bucket names
- urls:
    - `https://<BUCKET_NAME>.s3.<REGION>.amazonaws.com/<FILE_NAME>`
    - `https://hello.s3.us-east-1.amazonaws.com/picture.png`
- responds with a [[HTTP]] 200 if upload is successful
- key: name of object/file
- value: data itself, bytestream
- version id: multiple versions of same object
- metadata: content-type, last-modified, etc.
- data spread accross multiple devices and facilities (can be accross multiple [[Availability Zone|AZ]]s but not always)
- [[High Availability|highly available]] and [[Durability|durable]]
    - 99.95% - 99.99% service availability
    - 99.999999999% [[durability]]
- [[S3]] standard
    - default version of [[S3]]
    - data stored redundant accross multiple devices and multiple facilities (>= 3 [[Availability Zone|AZ]])
    - 99.99% availability
    - 99.999999999% durability
    - frequent accessed data
    - suitable for most workloads
- [[S3]] offers tiered storage for different use cases
- securing data
    - server side [[encryption]] - default [[encryption]] on bucket to encrypt all new objects
    - access control lists ([[Access Control Lists|ACLs]]) - which groups or accounts are granted access and what kind of access they have - down to the object level
    - bucket policies - specific actions for all buckets in an account (PUT but not DELETE)
- strong [[read-after-write consistency]]
    - adding a new object makes it immediately available for access
    - adding a new version of an object makes it imidiately accessible when accessing the object
    - can perform a list immediately after writing an object and changes will be reflected
- [[S3]] is a globally universal namespace