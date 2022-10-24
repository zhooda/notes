- elastic compute cloud ([[EC2]])
  - secure resizable compute capacity in the cloud
  - virtual machine in the cloud
  - capacity you want when you need it
  - control of your own instances
- pay for what you use
- no wasted capacity
  - select what you need now
  - grow and shrink as you grow
- on-prem = estimate capacity
  - long term investment, 3-5 years
  - lots of wasted capacity
  - time to provision a server is long
- [[EC2]] instance provisioned in minutes
- instance pricing options
  - on-demand
    - pay by the hour/second
  - reserved
    - reserve for 1 or 3 years
    - up to 72% discount on hourly rate
    - paying more upfront = more discount
  - spot
    - purchase unused capacity
    - up to 90% discount on hourly rate
    - prices fluctuate with supply and demand
  - dedicated
    - physical [[EC2]] server
    - dedicated for your use
    - most expensive option
- **on-demand instances**
  - low cost and flexibility w/o commitment
  - testing/dev purposes
  - short term
  - spiky, unpredictable workloads
  - cannot be interrupted
- reserved instances
  - predictable usage
  - specific capacity requirements
  - pay upfront to reduce costs
  - up to 72% off on-demand price
  - convertible RI
    - up to 54% discount
    - option to change to different RI type with greater or equal value
  - schedule RI
    - launch within the time window you need
    - match capacity reservation to predictable recurring schedule
    - short amounts of time (day, week, month)
  - operate at a regional level
    - can't apply reservation in different [[region]]
- spot instances
  - spot price fluctuates
  - applications w/ flexible start and end times
  - cost sensitive applications
  - urgent need for large amounts of additional capacity
  - image rendering
  - genomic sequencing
  - algorithmic trading
- dedicated hosts
  - compliance
  - no multi-tenant virtualization
  - legacy licensing
  - can be purchased on-demand
  - reserve for up to 70% discount
- 