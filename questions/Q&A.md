# **Cloudera Administrator Questions & Answers**

1.	**Which OS are supported by Cloudera Data Platform?**
	-	**Ans:** Oracle Linux, Redhat and Centos
	
2.	**Which platforms database platforms are supported by Cloudera?**
	-	**Ans:**	OracleDB, PostgreSQL, MySQL and MariaDB

3.	**Mention three features provided by  Cloudera Manager**
	-	**Ans:**	Install cluster, Configure cluster and Monitor cluster
	
4.	**How many clusters cna you manage with one instance of cloudera manager?**
	-	**Ans:**	Multiple clusters

5.	**What is a role group?**
	-	**Ans:**	A group of role instances to simply configuration.
	
6.	**Which are posible actions upon a stale configuration?**
	-	**Ans:**	Restar services, redeploy client configuration, refresh services.

7.	**What is a host template?**
	-	**Ans:**	A list of roles that can be assigned to one or more hosts by applying the template.

8.	**Which are things you can do with CM**
	-	**Ans:**	Delete a host from the cluster, add a new host to the cluster, add a new service to the cluster.

9.	**What is the default block size for HDFS?**
	-	**Ans:**	128 MB

10.	**What is the default replication factor for HDFS?**
	-	**Ans:**	3
	
11.	**Which features of HDFS provents data from being corrupted?**
	-	**Ans:**	Checksums

12.	**Mention three tools for data ingest in a Hadoop cluster**
	-	**Ans:**	Apache Kafka, Apache NiFi and Apache sqoop.

13.	**Why should you consider compresing data?**
	-	**Ans:**	Compressed files take up less space.

14.	**Mention three supported Hadoop file format**
	-	**Ans:**	CSV, Parquet, Avro

15.	**Mention three features of apache NiFi**
	-	**Ans:**	Data Governance, Flow Templates and Guareanted delivery

16.	**How many nodes do you need to run NiFi?**
	-	**Ans:**	NiFi can run on a single node or on multiple nodes.

17.	**How do you operate Nifi?**
	-	**Ans:**	Through a WebUI

18.	**What is the name of the NiFi software component that gets deployed on edge system?**
	-	**Ans:**	MiNiFi

19.	**Mention three description of Apache Kafka**
	-	**Ans:**	Fault Tolerant, Low latency, Scalable.

20.	**Mention three descriptions about topics in Apache Kafka**
	-	**Ans:**	Topics contain messages, Topics can be partitioned, Topics can be replicated.

21.	**What is the name of worker nodes in Apache Kafka?**
	-	**Ans:**	Brokers

22.	**What is CDP Private Cloud Base?**
	-	**Ans:** It is an on-premises version of Cloudera Data Platform.

23.	**CDP Private Cloud Base is the combination of which two products?**
	-	**Ans:**	Cloudera Enterprise Data Hub and Hortonworks Data Platform (HDP) and of course some new features and improvements.
	
24.	**Which are the supported JDKs for CDP Private Cloud Base 7.1.x?**
	-	**Ans:**	OpenJDK 1.8, OpenJDK 11, Oracle JDK 1.8

25.	**What are the requirements of JDK?**
	-	**Ans:**	It must be 64bits, the same version on each host and must be installed at /usr/java/jdk-version*
	
26.	**Mention two benefits of using Auto-TLS**
	-	**Ans:**	
	-	Auto-TLS automates the creation of an internal certificate authority (CA).
	-	All services will automatically have TLS configured and enabled.

27.	**Which services need a database for their own metadata?**
	-	**Ans:**	
	-	Cloudera Manager Server
	-	Oozie Server
	-	Sqoop Server
	-	Reports Manager
	-	Hive Metastore Server
	-	Hue Server
	-	Ranger
	-	Schema Registry
	-	Streams Messaging Manager

28.	**What is Cloudera Runtime?**
	-	**Ans:**	It is the core open-source software distribution within CDP that Cloudera maintains, supports, versions, and packages as a single entity.
	
29.	**What Cloudera Runtime does not include?**
	-	**Ans:**	
	-	Cloud services like Data Hub, DWX and MLX
	-	Management console, Workload Manager and Replication Manager
	-	Data Catalog
	-	Add-on products such as CDSW, CDF, Cloudera DataFlow,etc

30.	**CM Server maintains the state of the cluster in words of two categories, which are they?**
	-	**Ans:**	Model and Runtime

31.	**What is the Model State**
	-	**Ans:**	How the cluster is supposed tu run, where and what configuration is supposed to run within.
	
32.	**What is Runtime State**
	-	**Ans:**	It captures the processes, where and what commands are currently running.

33.	**When you update a configuration on 15 datanodes, which state are you updating?**
	-	**Ans:**	Model state

34.	**Mention four services that should run on a master host**
	-	**Ans:**
	-	HDFS NAmeNode
	-	YARN ResourceManager
	-	Job History Servers
	-	Zookeeper

35.	**Mention three roles that run on worker hosts**
	-	**Ans:**	
	-	HDFS DataNode
	-	YARN NodeManager
	-	Impala Daemons

36.	**Which kind of hosts do not run daemons?**
	-	**Ans:**	Gateway hosts
	
37.	**One instance of CM Private Cloud can manage multiple clusters**
	-	**Ans:**	True
	
38.	**Which type is going to be the first cluster created on CM?**
	-	**Ans:**	Regular
	
39.	**Which types of clusters we can add after the first one?**
	-	**Ans:**	Regular or Compute cluster
	
40.	**It is a set of roles distributed across multiple hosts with the same configuration**
	-	**Ans:** Role Group
	
36.	**Propierties can be set at which different levels?**
	-	**Ans:** Service, Role Group and Role Instance
	
36.	**Cloudera Manager deploys configuration settings to?**
	-	**Ans:** Cloudera Manager Agents and they are responsible for deploying those configuration settings.
	
36.	**Where are the configuration settings saved after their deployment by the Agents?**
	-	**Ans:**	The settings are save to local files.
	
36.	**Is it true that client and service configuration settings are stored seperately?**
	-	**Ans:** Yes
	
36.	**What is the default location for service daemon configuration files?**
	-	**Ans:** /var/run/cloudera-scm-agent/process
	
36.	**What is the frecuency that a DataNode sends a heartbeat to the Namenode to let him know that it's available?**
	-	**Ans:**  Every 3 seconds
	
36.	**What is a category of funtionality on Cloudera Manager?**
	-	**Ans:** Service 
	
36.	**What does represent an individual or seperate running process or component on a Host in CDP Cluster?**
	-	**Ans:** Role Instance

36.	**It is a set of configuration properties**
	-	**Ans:** Role Group
	
36.	**You want to add 3 nodes in the cluster and they should have the same service running on the cluster.   Which feature can you use to add 3 nodes and having the same services running on that?**
	-	**Ans:** Host template
	
36.	**For Cloudera Manager, it represents the configuration of Cloduera Manager and all the clusters it manages**
	-	**Ans:** Deployment

36.	**Represents a physical entity which contains a set of physical hosts and typically served by the same switch**
	-	**Ans:** Rack

36.	**This is a set of configuration properties for a set of role instances**
	-	**Ans:** Role Group

36.	**It is a named configuration of resources and a policy for scheduling the resources among YARN applications**
	-	**Ans:** Dynamic Resource Pool
	
36.	**Each individual cluster can only be associated with a single Cloudera Manager Server**
	-	**Ans:** True

36.	***In a single CDP Cluster, we can have more than one Cloudera Runtime Environment**
	-	**Ans:**  False

36.	**A single Host of CDP cluster can join more than one CDP Cluster, which all are managed by a Single Cloudera Manager**
	-	**Ans:** False

36.	**Gateway node role can be used to provide access to a client for a specific service from cluster services**
	-	**Ans:** True

36.	**Is it mandatory to have Name for the Gateway Role**
	-	**Ans:** Yes

36.	**Hue Kerberos Ticket Renewer is a gateway role that proxies tickets from kerberos**
	-	**Ans:** True
		
36.	**Agent from each host send the heartbeath every 15 seconds to Cloudera Manager Server**
	-	**Ans:** True
	
36.	**Which Linux kernel features allows for restricting Linux processes?**
	-	**Ans:** cgroups
		
36.	**Which is the default YARN scheduler in CDP?**
	-	**Ans:** Capacity Scheduler
	
36.	**Jobs are sent to what type of queues?**
	-	**Ans:**  Leaf Queues

36.	**What is the name of Impala’s feature to manage utilization?**
	-	**Ans:**  Admission Control
	
36.	**A modified cofiguration may requiere one or both of which actions?**
	-	**Ans:**
		Client redeployment
		Role Instance Restart or refresh

36.	**What is the purpose of Acvanced configuration snippets (safety values) in Cloudera Manager?**
	-	**Ans:**  It is used to overide setting for properties not exposed in Cloudera Manager and define additional configurations.
	
36.	**Cloudera Manager Agent pulls daemon configuration settings from Cloudera Manager Server and stores it on disk**
	-	**Ans:**  True

36.	**What is the default location for service daemon config files?**
	-	**Ans:** /var/run/cloudera-scm-agent/process
	
36.	**What is the default client configuration location?**
	-	**Ans:** /etc/hadoop/config
	
36.	**Client configuraton fiels are generated by CM when?**
	-	**Ans:**  
		A cluster is created
		A service or a gateway role is added on a host
	
36.	**When you remove a host from the cluster, what is going to be preserved in the host?**
	-	**Ans:** Data directories
	
36.	**Clusters DO NOT need to run the same mayor version of CDP or Cloudera Runtime**
	-	**Ans:** True
	
36.	**What is the only restriction when adding a cluster, in terms of version?**
	-	**Ans:** CM needs to be equal or greater than the version that you're adding the cluster for
	
36.	**What is the main purpose of NFS Gateway?**
	-	**Ans:** Allows a client to mount HDFS as part of the local file system
	
36.	**Minimum HDFS daemons for HDFS without HA?**
	-	**Ans:** NameNode, DataNode and Secondary NameNode
	
36.	**NameNode Metadata is loaded from disk to RAM when the NameNode daemon startups**
	-	**Ans:** True
	
36.	**What is the recocommended Java Heap size?**
	-	**Ans:** At least 1GB for every million HDFS blocks
	
36.	**What is the default Java heap size on the NameNode?**
	-	**Ans:** 1GB
	
36.	**What is stored in the NameNode's Metadata?**
	-	**Ans:** Items, an item would be a file name, file ownership and permissions.  An item would be the name an location of each of the blocks.
	
36.	**A category of functionality on Cloudera Manager**
	-	**Ans:** Service
	
36.	**It represents an individual or seperate running process or component on host in CDP Cluster**
	-	**Ans:**  Role Instance
	
36.	**A set of configuration properties in CM?**
	-	**Ans:** Role Group
	
36.	**In CM, It represents one of the running service**
	-	**Ans:** Instance
	
36.	**Each service can have more thatn one of this in CM**
	-	**Ans:** Role
	
36.	**For CM, it represents the configuration of CM and all the clusters it manages**
	-	**Ans:** Deployment
	
36.	**In CM, it represents a physical entity which contains a set of physical hosts and typically served by the same switch**
	-	**Ans:** Rack
	
36.	**This is a set of configuration properties for a set of Role Instances**
	-	**Ans:** Role Group
	
36.	**It is a named configuration of resources and a policy for scheduling the resources among YARN applications**
	-	**Ans:**  Dynamic Resource Pool
	
36.	**With HDFS HA, Active NameNode writes metadata changes to a quorum of JournalNodes.  It means, with HA, edits log is kept on JournalNodes instead of NameNode**
	-	**Ans:**  True
	
36.	**In HDFS, Standby NameNode reads from the JournalNodes to stay in sync with the active NameNode**
	-	**Ans:** True
	
36.	**Which setting controls the number of threads that listen to requests from clients?**
	-	**Ans:** dfs.namenode.handler.count 

36.	**Which setting indicates the number of volumes to fail before the datanode takes itself offline?**
	-	**Ans:** dfs.datanode.failed.volumes.tolerated 
	
36.	**Which setting controls the maximum amount of memory (in bytes) a datanode can use for caching?**
	-	**Ans:** dfs.datanode.max.locked.memory
	
36.	**What additional daemons are needed to go to high availability with automatic failover?**
	-	**Ans:** 
		-	An additional NameNode
		-	Failover Controllers
		-	Journal Nodes
	
36.	**After High Availability is enabled, some manual configurations that may be needed include:**
	-	**Ans:**
		-	Update the Hive Metastore
		-	Run invalidate metadata command in Impala Shell
		-	Add the httpFS role if not already on the cluster

36.	**Is it true that distcp turns the copy process into a MapReduce job?**
	-	**Ans:** True
	
36.	**What about several distcp copies executions of the same entire directories?**
	-	**Ans:** Files previously copied will be skipped.  The only check for duplicate files is that the file's name, size, and checksum are identical.

36.	**What is the meaning of every number of CDP version, for example CDP 7.1.6?**
	-	**Ans:**
		- 7 = Major version
		- 1 = Minor update
		- 6 = maintenance update
	
36.	**What are the two ways to upgrade CDP?**
	-	**Ans:**  Parcels and Package
	
36.	**What is the rule between Cloudera Runtime and CM?**
	-	**Ans:** CM minor version must be >= Cloudera Runtime minor version
	
36.	**When we are upgrading cloudera manager agents, how can I determine which packages may be installed or upgraded?**
	-	**Ans:** yum deplist cloudera-manager-agent
	
36.	**What command checks for missing or corrupt data blocks?**
	-	**Ans:** hdfs fsck
	
36.	**Which of the following commands will get the safemode status of your cluster?**
	-	**Ans:** hdfs dfsadmin -safemode get 

36.	**What are some reasons to invoke a rebalance of the cluster?**
	-	**Ans:**
		-	Some nodes have much more data on them than others
		-	A new host is added to the cluster
		-	You can view the capacities from the NameNode GUI DataNode tab
		
36.	**Required steps in moving a host between clusters?**
	-	**Ans:**
		-	Decommission the host 
		-	Remove all roles from the host (except for the Cloudera Manager management roles) 
		-	Remove the host from the cluster but leave it available to Cloudera Manager 
		-	Add the host to the new cluster
	
36.	**In Monotoring Terminology, what is an Entity?**
	-	**Ans:** A Cloudera Manager component with metrics associated with it.  Example: clusters, services, roles, and role instances, hosts.
	
36.	**In Monotoring Terminology, what is a Metric?**
	-	**Ans:** A property that can be measured.  Example: RAM Utilization, Total HDFS Storage capacity
	
36.	**In Monotoring Terminology, what is a chart?**
	-	**Ans:** Customizable display aggregated metrics for entities over time
	
36.	**In Monotoring Terminology, what is a Dashboard?**
	-	**Ans:** A page displaying key entity information and charts.  A dashboard consists of a set of charts.
	
36.	**What are pass-fail tests?**
	-	**Ans:** Tests to respond if the things are good or bad
	
36.	**What is a canary test**
	-	**Ans:** It responds if the service is working or not.  It is a kind of pass-fail test
	
36.	**What does the metric tests?**
	-	**Ans:**  They compare a number or value to a threshold.  The result is good, bad or concerning
	
36.	**How often fsimage file is automatically updated by default?**
	-	**Ans:** Every hour or 1 million transactions.
	
36.	**What are common source of cluster problems?**
	-	**Ans:**
		-	Misconfiguration
		-	Hardware exhaustion
		-	Resource exhaustion		
	
36.	**What should you do to ensure hostname resolution?**
	-	**Ans:**	Test forward and reverse DNS lookups
	
36.	**Mention an HDFS subcommand**
	-	**Ans:** getconf
	
36.	**What are the import security terms in Cloudera**
	-	**Ans:** Security, Authentication, Authorization and Encryption
	
36.	**Hadoop daemons can use Kerberos to authenticate all remote procedure calls (RPCs)**
	-	**Ans:** True
	
36.	**What are keytab files in Kerberos?**
	-	**Ans:**
		-	Stores kerberos principals and associated keys
		-	Allows non-interactive access to service protected by kerberos
	
36.	**Mention an open source application to define, administer, and manage security policies in CDP**
	-	**Ans:**  Apache Ranger
	
36.	**what the phrase "single pane of glass" means for security administrators?**
	-	**Ans:** One place to go to, one centralized administration area for you security policies
	
36.	**Is it true that encryption requires us of Active Directory**
	-	**Ans:** True
	
36.	**Kubernetes is often abbreviated as?**
	-	**Ans:** k8s
	
36.	**Mention 3 trues of Cloud-Native Architecture**
	-	**Ans:**
		-	Object stores are the preferred way to store data
		-	Containers enable more efficient distribution of resources
		-	Storage and copute can be seperated due to fast networking
	
36.	**Is it true in CDP Public Cloud that your data will always run under your control in your VPC**
	-	**Ans:** Yes, It is true
	
36.	**Mention 3 trues about Workload Manager (VXM)**
	-	**Ans:**
		-	It will need connectivity to NiFi to ensure all log files flow into it
		-	It tracks only current statistics at this time; historical metrics are not taken into account
		-	It cannot be setup on-premises (Cloud only)
	
36.	**Mention a true of auto-scaling**
	-	**Ans:** It enables scaling up or down of virtual warehouse instances
	
36.	**What is the recommended disk configuration for a CDP Cluster?**
	-	**Ans:** JBOD
	
36.	**What's the meaning of Fencing in HA HDFS?**
	-	**Ans:** Isolating a failed NameNode
	
36.	**What is the component that will start the Map or Reduce Task?**
	-	**Ans:** TaskTracker
	
36.	**Mention 3 roles that should be on a worker node**
	-	**Ans:**
		-	NodeManager
		-	Impalad	
		-	Zookeeper
		
36.	**Metrics are available on?**
	-	**Ans:** Hosts, services, roles and instances.

36.	**What roles you need for HDFS HA?**
	-	**Ans:** 
		-	Journal
		-	Failover Controllers
		-	NameNode (Active)
		-	NameNode (Standby)
		
36.	**What evaluates the Host Inspector?**
	-	**Ans:**
		-	Validates OS Settings
		-	Networking Settings
		-	System Time
		-	User and Group Settings

36.	**what are the Ranger Audit Tabs?**
	-	**Ans:**
		-	Access
		-	Admin
		-	Login sessions
		-	Plugins
		-	Plugin status
		-	User Sync

36.	**What are the Audit Filter Options?**
	-	**Ans:**
		-	User
		-	Application
		-	Exclude User

36.	**Mention the ways to Rebalance HDFS?**
	-	**Ans:**
		-	Shell-script
		-	CM UI

36.	**What options do you have in HDFS File Browser?**
	-	**Ans:**
		-	Utilization Report
		-	Storage Quotas
		-	Snapshot Management
			
36.	**You can create HBase and HDFS Snapshots**
	-	**Ans:** True
	
36.	**Snapshots can improve data replication performance**
	-	**Ans:** True
	
36.	**You can take snapshots by HDFS Browser or by Snapshot Policies in CM**
	-	**Ans:** True
	
36.	**Which two options do yo have for Alerts delivery**
	-	**Ans:** Email and SNMP
	
36.	**What are the Cloudera Manager External Authentication Types?**
	-	**Ans:**
		-	AD
		-	LDAP
		-	SAML
	
36.	**In Health Tests, services and hosts are noted as?**
	-	**Ans:**
		-	Good
		-	Concerning
		-	Bad
	
36.	**What are the two Ranger types of policy?**
	-	**Ans:** 
		-	Resource-based
		-	Tag-based
	
36.	**What are the two CDP options for Data Durability?**
	-	**Ans:**
		-	Replication through HDFS
		-	Erasure Coding (EC)
	
36.	**Give the list of Event Types in CM**
	-	**Ans:**
		-	Activity_Event
		-	Audit_Event
		-	Health_Check
		-	Log_Message
	
36.	**What are the Health Alerts tagas for Threshold?**
	-	**Ans:** Bad and Concerning	
		
		
		
		
		
		
		
		
		
		
		
		
		
		
