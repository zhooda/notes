# Databases 03 - Amazon Aurora

- what is [[Amazon Aurora]]
	- Amazon proprietary database
	- [[MySQL]] and [[PostgreSQL]] compatible [[RDBMS]] engine
	- speed and availability of high-end commercial databases
	- cost-effectiveness of open-source databases
- performance
	- up to 5x performance from [[MySQL]]
	- up to 3x performance from [[PostgreSQL]]
	- lower price point
	- similar availability
- basics
	- starts with 10GB
	- scales in 10GB increments up to 128TB
	- storage Auto Scaling
	- compute resources can scale to 96 vCPUs and 768GB [[RAM]]
	- 2 copies of data are contained in each [[Availability Zone|AZ]]
		- minimum of 3 [[Availability Zone|AZs]]
	- always have 6 copies of your data
- scaling
	- transparently handle loss of 2 copies of data without affecting write availability
	- lose 3 copies without affecting read availability
	- storage is self-healing
		- data blocks and disks continuously scanned for errors and repaired automatically
- types of replicas
	- [[Amazon Aurora]] replicas
		- up to 15 read-replicas
		- async replication (milliseconds)
		- low performance impact on primary
		- in-region
		- automatic failover (no data loss)
	- [[MySQL]] replicas
		- up to 5 read-replicas
		- async replication (seconds)
		- high performance impact on primary
		- cross-region
		- automatic failover (potentially minutes of data loss)
	- [[PostgreSQL]] replicas
		- up to 5 read-replicas
- backups
	- automated backups always enabled
	- don't impact db performance
	- take snapshots without impacting performance
	- share snapshots with other accounts
- serverless
	- on demand auto scaling
	- cluster that auto starts/stops and scales up/down based on capacity needs 
	- pay when in use

Review
- 2 copies in each [[Availability Zone|AZ]]
- minimum of 3 [[Availability Zone|AZs]]
- 6 copies of data
- share snapshots with other AWS accounts
- 3 types of replicas
	- automated failover only available on aurora replicas
- automated backups enabled by default
- serverless for simple cost effective infrequent, intermittent or unpredictable workloads
-