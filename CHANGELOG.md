# Change Log
All notable changes to this project will be documented in this file.

## [1.3.0] 2017-01-20
### Added
- PNDA-2533: Ability to create an ElasticSearch cluster for external usage
- A new motd when login to nodes via SSH

### Changed
- PNDA-2121: Improve jupyter sls files
- PNDA-2239: The 'pnda' user and 'pnda' group are able to write/delete files written by Gobblin which now runs as 'pnda' user instead of 'gobblin' user
- PNDA-2467: Put platform-data-mgmt in a virtualenv
- PNDA-2468: Put platform-deployment manager in a virtualenv
- PNDA-2469: Put platform-package-repository in a virtualenv
- PNDA-2484: Put hdfs-cleaner in a virtualenv
- PNDA-2485: Pin all versions of pnda python components and upgrade the version of libraries
- PNDA-2489: Remove _modules/zk.py file and move it to _modules/pnda.py and do simple REST queries instead of using cm-api
- PNDA-2542: Put elastic-search-curator in a virtualenv
- PNDA-2544: Download Zookeeper from top level mirror instead of US mirror
- PNDA-2547: Put impala-shell in a virtualenv
- PNDA-2550: kibana dashboard are now imported without elasticdump, which simplifies the installation
- PNDA-2551: Put Jupyter python components in a virtualenv
- PNDA-2552: Put graphite of the console in a virtualenv
- PNDA-2560: Put cm_setup cloudera installation script in a virtualenv
- PNDA-2598: Put pnda_restart script in a virtualenv

### Fixed
- PNDA-2494: Concurrency issue during deployment related to master dataset creation
- PNDA-2498: Deployment-manager was passing the wrong thrift server to the Happybase library
- PNDA-2511: Pin version of nodejs to avoid installation failure of kibana
- PNDA-2543: Make the creation of the cloudera manager external database idempotent

## [1.2.0] 2016-12-12
### Added
- PNDA-2250: Provide tools that allow pnda infra to be rebooted and the services started again
- Aggregating redundant services into common VMs (anti-affinity on OpenStack)

### Changed
- PNDA-2284: hdfs-cleaner creates the archive container it needs
- PNDA-1918: Simplify component paths 
- PNDA-2392: Refactor hue user creation 
- Update CDH to 5.9.0
- PNDA-1812: Add a re-apply config mode to cm_setup
- Merge general zookeeper/kafka white and black box tests
- PNDA-2487: Increase HBase heaps for CDH5.9 
- PNDA-2496: CM now uses external MySQL database instead of embedded postgres db

### Fixed
- PNDA-2231: Don't fail if the pnda user is already created in grafana 
- Change 'heap_dump_directory_free_space' warnings for PICO flavor
- Update logshipping for gobblin
- PNDA-2431: Reduce impala catalog server heap size for pico 
- Fix UTF8 issue on master-dataset
- PNDA-2434: Pin version of ES curator and specify full path 
- PNDA-2435: Reduce ES data retention for pico 
- Create a python virtualenv for platform testing
- PNDA-2488: Harmonize heap dump warning and reduce firehose size 
- Fix issue on DM config as OpenTSDB configuration should be IP:PORT not a link
- Alter YARN parameters to give 512MB map tasks
- PNDA-2487: Adjust hbase, yarn and mapred to better fit pico 

## [1.0.1] 2016-10-31
### Fixed
 - PNDA-2368: Include console-backend 0.2.2 to fix version of the redis-parser npm module to 2.0.4

## [1.0.0] 2016-10-21
### Added
- Multi-flavor mechanism, with pico flavor
- PNDA-2320 Kafka manager port is now in pillar
- PNDA-2272 review formulas in order to ensure no issue on deployment even if there is not all roles
- PNDA-2233 Jupyter notebook plugin added to deployment manager

### Fixed
- Some logs were not in /var/log/pnda and so, were not shipped to the logserver
- The 'bulk' directory in HDFS is now owned by the 'pnda' user
- Prevent Gobblin from ingesting internal kafka __consumer_offsets topic

### Changed
- ntp:servers pillar default was removed, but can still be set

## [0.2.0] 2016-09-07
### Added
- Install Jupyter-Spark extension
- Add default Grafana dashboards for PNDA metrics
- PNDA-2010 Create Graphite datasource
- Add a simple minimal notebook to explain basic Jupyter usage
- Create PNDA OpenTSDB default datasource in Grafana
- PNDA-820 Added graphite formula to salt

### Fixed
- PNDA-2022 Re-raise exceptions from cm_setup for fail fast behaviour
- PNDA-2009 Tell upstart to not log console output of data-logger
- PNDA-1933 CM setup waits on cloudera manager being available
- Do not use http download for cloudera manager
- Clean ups to Grafana states
- Clean ups to OpenTSDB states
- Clean ups to Jupyter states

### Changed
- PNDA-2012 Update to Grafana 3.1.1
- PNDA-1485 Update OpenTSDB to 2.2.0
- PNDA-2016 Update Zookeeper to 3.4.6
- Update Kafka Manager to 1.3.1.6
- Update Kafka to 0.10.0.1
- Use saltenv instead of env in anticipation of upcoming Salt Boron
- Automatically set test topic replication based on broker cluster size
- Make the pnda user home directory configurable
- For AWS, launch PNDA on private network
- PNDA-1923 Add the yarn daemon and application logs to logserver
- PNDA-2005 Add a state that creates a PNDA test topic on Kafka instead of using KM 

## [0.1.0] 2016-07-01
### First version
- Creates and configures all PNDA services
