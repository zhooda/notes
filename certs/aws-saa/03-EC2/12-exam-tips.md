# EC2 12 - Exam Tips

- [[EC2]]
  - virtual machine in AWS
  - select capacity you need right now
  - pay for what you use
  - only minutes to provision
  - pricing
    - on-demand
      - pay by second or hour
      - flexibility
    - spot
      - purchase unused capacity
      - discount up to 90%
    - reserved
      - reserve capacity from 1 to 3 years
      - up to 72% savings
    - dedicated
      - physical [[EC2]] server dedicated for your use
- [[Command Line Interface|CLI]]
  - least privilege
  - use [[IAM]] groups
  - secret access key - only see this once
    - `aws configure`
  - don't share access key pairs
  - supports linux, mac, win
- Roles
  - preferred option from security perspective
  - avoid hard coding credentials
  - policies control roles permissions
  - updates to policies take effect immediately
  - attach or detach roles to running [[EC2]] instances
- Security Groups
  - changes to security groups take effect immediately
  - any number of [[EC2]] instance in a security group
  - multiple groups attached to [[EC2]] instances
  - all inbound  traffic is blocked by default
  - all outbound traffic is allowed by default
- Bootstrap Scripts
  - runs when instance first runs
  - root level
  - install applications before server launch
- User Data
  - bootstrap scripts
- Metadata
  - data about [[EC2]] instances
  - use bootstrap scripts (user data) to access metadata
- Networking
  - [[ENI]]
    - basic networking
    - management network
    - logging network
    - low cost
    - multiple [[ENI]] for each network
  - [[EN|Enhanced Networking]]
    - 10 Gbps - 100 Gbps
  - [[EFA]]
    - [[High Performance Computing|HPC]], [[Machine Learning|ML]]
    - OS-bypass
- Placement Groups
  - cluster placement group
    - low network latency, high [[throughput]]
    - [[High Performance Computing|HPC]]
    - can't span multiple [[Availability Zone|AZ]]s
  - spread placement groups
    - critical [[EC2]] instance on different hardware
  - partition placement groups
    - multiple [[EC2]] instances
    - [[HDFS]], [[Apache HBase|HBase]], [[Apache Cassandra|Cassandra]]
- Dedicated Hosts
  - special licensing or compliance requirements
  - [[EC2]] dedicated host = physical dedicated server for you 
  - bring per-socket/per-core/per-vm license
- Spot Instances & Fleets
  - instance can save 90%
  - stop from terminating with Spot Block
  - don't need persistent storage
  - fleet is collection of spot instances and optionally on-demand instances
- [[vCenter]] via [[VMware]] on AWS
  - extending [[vmware]] cloud to AWS public cloud
    - cloud migration
    - AWS tools
    - disaster recovery
- Outposts
  - outposts rack for large deployments
  - outposts servers for small deployments