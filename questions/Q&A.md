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

10.	**What is the default replication factor fro HDFS?**
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
	
36.	** **
	-	**Ans:**	



		
		
		
		
		
		
		
		
			
		
		
		
		
		
		
		
		
		
		
		
		
		
		
		
		
		
		
		
		
		
		
		
