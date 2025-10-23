## Object Storage
Problem with traditional storage is that the file system of a traditional system is too limited for the massive scale of the internet.

### File Storage:
- Analogy: A digital filing cabinet with folders inside folders
- How it works: Data is stored in files, which are organized in directories
- Best for: shared documents, user home directories
- Limitation: Performance degrades as scale increases and the complex permissions
### Block Storage:
- Analogy: A book (a block) on a numbered shelf in a library. The operating system knows which shelf numbers make up the whole story
- How it works: Data is split into fixed size blocks, each with unique addresses
- Best for: Databases, VM disks (High performance, low-latency needs)
- Limitation: Lacks metadata; not meant for direct file access over web
### Object Storage:
- Analogy: You hand over your car (the data) and get a ticket (a unique ID). The ticket has all the info needed to retrieve your specific car from a massive parking lot. You don't care where it's parked
- How it works: Data is bundled with rich metadata and a globally unique ID, all stored in a flat address space (a storage pool)
- Best for: Unstructured data at scale: photos, videos, backups, log files, website assets

### GCS - Google Cloud Storage
Google's unified, infinitely scalable, highly durable, and cost effective object storage service
- Uses buckets
##### Buckets
- part of it is Binary large object (BLOB) storage
- Can be online content, backup and archiving storage of intermediate results
- Buckets have unique names and a geographic location
- Buckets have immutable objects
- User access to Buckets are controlled with ACLs
### Lifecycle Policies
Large amounts of object data can quickly become expensive. For this you can use lifecylcle managment policies.
Examples:
1) Delete objects older than 365 days
2) Delete objects created before mm/dd/yyyy
3) Keep only the 3 most recent versions
### Key differentiators of GCS
- Global Namespace: Bucket names are universal
- Exceptional Durability: Boasts 99.9999999% annual durability.
- Location Types: Region vs Dual-Region vs Multi-Region (tradeoffs between latency, availability and cost)
- Storage Classes: Standard, Nearline, Coldline, Archive
- Integration & Security: IAM & Encryption, Direct Connect, Analytics Ready
### GCS Location Types
- Regional: Best for applications requiring the lowest latency and cost within a specific area. Especially for data sovereignty, but offers less resilience against region-wide outages and higher latency for global users.
- Multi-Region: Provides maximum availability and low latency content delivery across a broad geographic area, making it ideal for critical data and global applications, but this resilience comes at a higher cost and with less precise control over data placement
- Dual-Region: Provides the disaster recovery resilience of a multi region with the high performance access of a regional bucket, but this benefit is targeted at dual area

### Storage Classes
- Standard: For hot data, highest cost to store, lowest access cost use for website content, active data
- Nearline: For data accessed less than once a month, good for backups
- Coldline: For data accessed less than once a quarter good for disaster recovery
- Archive: For data accessed less than once a year, Lowest storage cost, highest access cost. Use for long-term archiving, compliance
- Example Rule: "After 30 days, move all objects from standard to nearline, after 365 days, delete them.
#### Security & Access Control
- The principle of leas privilege: Only grant the permissions that are absolutely necessary
- IAM (Identity and Access Management): Who? (The principle ->) Can do what
- Signed URLs
- Public Access
#### Common Use Cases
- Data Lake Foundation: Storage massive raw data for analytics with BigQuery & Dataproc
- Backup & Archiving: Cost-effective and durable storage for database backups and compliance data
- Static Content Delivery: Serve website images, videos, and static files, often paired with a CDN
- Media Storage & Streaming: Store and serve large media files for applications
#### Storage Types (WIP):
- Structured data:
- Unstructured data:
- Transactional data:
- Relational data:
