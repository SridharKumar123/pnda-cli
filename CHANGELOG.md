# Change Log
All notable changes to this project will be documented in this file.

## [Unreleased]
### Added
- PNDA-3127: Post ingress compaction for Kafka datasets
- PNDA-4449: Add a consul_server grain
- PNDA-4428: Add Flink role grains
- PNDA-4452: Install curl in bootstrap phase
- PNDA-4489: Option to set the port to use on the command line when calling the socks proxy setup script
- PNDA-4450: Set name tags for CFN resources
- PNDA-4398: Support Spark 2 for Oozie jobs
- PNDA-4131: Heat backend to provision PNDA on OpenStack via pnda-cli

### Changed
- PNDA-4394: Remove Anaconda CDH parcel mirror as this is now installed from a bundle
- PNDA-4420: Pre-seed salt minion keys
- PNDA-4490: Update production.json example to match the production flavour
- PNDA-4122: Remove scalable ELK
- PNDA-4525: Deprecate Ubuntu 14.04
- PNDA-4530: Refactor pnda_env.yaml to reflect that pnda-cli is no longer AWS specific
- PNDA-4523: Write ssh config when starting CLI
- PNDA-4558: Modify topology to use gateway instead of bastion

### Fixed
- PNDA-4415: Update PyYAML and requests
- PNDA-4203: Set up Consul DNS before running highstate and restart minions from pnda-cli after installing Consul
- PNDA-4453: Apply timeouts in thread.join
- PNDA-4448: Fixes to ADD_ONLINE_REPOS for redhat/centos
- PNDA-4498: Use wget instead of curl with apt-key
- PNDA-4441: Removed "extra-index-url" and "find_links" directives from pip and easy_install configurations

## [1.1.0] 2018-02-10
### Added
- PNDA-3127: Post ingress compaction for Kafka datasets
- PNDA-3299: Support multiple NTP servers properly
- PNDA-3599: Console output indicating any cloud formation stack errors
- PNDA-3598: Add a pre-check to validate the AWS region
- PNDA-3511: Export a bundle of resources used during provisioning to `cli/logs/<cluster>_<time>_bootstrap-resources.tar.gz` to help an operator with later operations tasks such as a recreating a failed node.
- PNDA-3630: Added EXPERIMENTAL flag to pnda_env.yaml which is initially only used to include Jupyter Scala support
- PNDA-3623: Add support for configuring Jupyter with SSL cert/key.

### Changed
- PNDA-3583: Hadoop distro is now part of grains
- PNDA-3365: Remove unnecessary explicit hostfile setup on bastion
- PNDA-3530: Ambari version 2.6.0.0 and HDP version 2.6.3.0
- PNDA-3487: /tmp is now tmpfs for production
- PNDA-3602: Update boto requirement to 2.48.0 for updated ec2 region support
- PNDA-4043: Update HDP to version 2.6.4.0
- PNDA-4052: Add log volume to jupyter node in standard flavor
- PNDA-4186: Deprecated PNDA-MINE_FUNCTIONS_NETWORK_IP_ADDRS_NIC field from pnda_env YAML
- PNDA-4179: Removed interface setup code from bootstrap scripts, expected to be done during infra preparation
- PNDA-4615: Major refactor into clearly separated back-ends to execute orchestration on different platforms
- PNDA-3524: Beacon related logic removed from codebase

### Fixed
- PNDA-3534: Make iptables injection script idempotent.
- PNDA-3552: Creation time improvements for large clusters when there is no bastion.
- Fork: Fixed issue with missing /etc/cloud directory failing install on baremetal
- PNDA-3629: Allow void arguments for specific invocation combinations e.g. no need to specify separate node counts for server cluster installs
- PNDA-4191: Salt rendering error for standard flavor in kafka settings.sls
- PNDA-3563: When the available volumes do not match the expected configuration defined in volume-config.yaml output a sensible error message at an early stage before doing anything to the disks
- PNDA-3553: Yarn resource manager logs and potentially others not aggregated on HDP
- PNDA-3537: If option missed and running in automation, resulting prompt causes EOF error to propagate to user
- PNDA-3512: Expand (with today's feature set) should work for server clusters/production
- PNDA-3559: existing machines def files use wrong node types: 'cdh-xxx' instead of 'hadoop-xxx'

## [1.0.0] 2017-11-24
### Added
- PNDA-3160: Added support for creating PNDA on existing server clusters
- PNDA-1960: Make Kafkat available on nodes as option for Kafka management at CLI
- PNDA-2955: Add pnda_env.yaml setting for choosing hadoop distro to install
- PNDA-3302: Upgrade edge flavor on pico
- PNDA-3218: Add iprejecter to enable offline env
- PNDA-3314: Add new flavor 'production' designed for larger, bare metal clusters
- PNDA-3484: Add CentOS support

### Changed
- PNDA-3186: Refactored code into CLI for creating PNDAs on many platforms (pnda-cli)
- PNDA-2965: Rename `cloudera_*` role grains to `hadoop_*`
- PNDA-3215: Remove EPEL repository
- PNDA-3180: When expanding a cluster limit the operations to strictly required steps on specific nodes
- PNDA-3444: Disallow uppercase letters in the cluster names due to AMBARI-22361 affecting HDP.

### Fixed
- PNDA-3499: Cleanup CHANGELOG with missing release info.
- PNDA-3200: socks_proxy script reuses existing ssh-agent instead of launching a new one if possible
- PNDA-3199: Make socks proxy script executable
- PNDA-3424: Add a retry to AWS API calls to work around SSL timeout errors
- PNDA-3377: fix issue on check config which required descriptor file

## [FORK]
- Applied annotation tag where pndaproject/pnda-aws-templates has been forked.
