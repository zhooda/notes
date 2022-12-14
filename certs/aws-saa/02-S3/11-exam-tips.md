- object based storage
- not for OS or DB storage
- files up to 5TB in size
- unlimited storage and objects
- files are stored in buckets
- bucket name needs to be globally unique
- bucket name in url: `name`.s3.`region`.amazonaws.com/`key`
- successful upload will return [[HTTP]] 200
- objects:
  - key = object name
  - value = data itself (byte sequence)
  - version id
  - metadata
- securing buckets
  - private by default
  - allow public access on bucket and objects to make public
  - object [[Access Control Lists|ACLs]] on individual objects
  - bucket policies to make entire buckets public
- hosting a static website
  - use bucket policies to make all objects public
  - static content only
  - [[S3]] has automatic scaling
- versioning objects
  - all versions stored in [[S3]]
  - deleting places delete marker over object version
    - restore object by deleting delete marker
  - once turned on you can't turn off versioning
    - only able to suspend it
  - lifecycle rules to change storage tiers of object versions based on time 
  - supports [[Multi-Factor Authentication|MFA]]
- storage tiers
  - standard
    - most workloads (websites, [[Content Delivery Network|CDN]], [[big data]] & analytics)
  - standard IA
    - long term infrequent critical data (backups, disaster recovery)
  - one zone IA
    - long term infrequent non-critical data
    - only 1 [[Availability Zone|AZ]]
  - glacier
    - long archiving
    - minutes to hours retrieval time
  - glacier deep archive
    - regulatory purposes, 7-10 year lifecycle
    - 12+ hours retrieval time
  - intelligent tiering
    - unknown or unpredictable access patterns
- lifecycle management
  - automates moving objects between storage tiers
  - can be used with versioning
  - can be applied to current and previous versions
- object lock
  - [[Write Once Read Many|WORM]] - [[write once read many]]
  - individual objects or bucket level
  - governance mode
    - users can't overwrite or delete without permisison
  - compliance mode
    - no one can overwrite or delete (even root)
  - glacier [[Write Once Read Many|WORM]] = vault lock
    - [[Write Once Read Many|WORM]] model
    - lock policy from future edits
- [[encryption]]
  - transit
    - [[Secure Sockets Layer|SSL]]/[[Transport Layer Security|TLS]]
    - [[HTTPS]]
  - rest SSE
    - SSE-[[S3]]  - [[AES]]-256
    - SSE-[[KMS]] 
    - SSE-C
  - rest CSE
    - encrypt before upload
  - bucket policy deny PUT that don't include the [[encryption]] header
- performance
  - prefixes = folder/subfolder
  - more prefixes = more performance
  - SSE-[[KMS]] has limits
    - cannot request quota increase
  - multi-part uploads, 100MB+
  - byte-range fetch downloads
- replication
  - replicate objects from bucket to bucket
  - objects in existing bucket not replicated automatically
  - delete markers not replicated by default