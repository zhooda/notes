- how computers communicate
  - [[ssh]]:   port   22
  - [[rdp]]:   port 3389
  - [[http]]:  port   80
  - [[https]]: port  443
- security groups
  - virtual [[firewall]] for [[EC2]] instance
  - everything blocked by default
  - let everything in with [[CIDR]] 0.0.0.0/0
- bootstrap script
  - script runs when instance first runs
  - runs at root level
  - automate installation of your applications
  - called "user data"
