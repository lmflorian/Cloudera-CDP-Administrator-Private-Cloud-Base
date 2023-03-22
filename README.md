Cloudera CDP Administrator Private Cloud Base
============================

This is a study guide I built while studying to get CDP Administrator  Private Cloud Base (CDP-2001) certification.  I wish it helps to someone interested while having a good time as I had.

This guide has all the documentation to achieve the CDP Administrator Private Cloude Base (CDP-2001) Certification, and at the same time it gives you the oportunity to learn all the tecnologies  to manage a CDP Cluster efficiency following best practices and recommendations from Cloudera.


Table of Contents
--------------------

**General Concepts**
-	[Cloudera Data Platform](#Cloudera-Data-Platform) 
-	[CDP Private Cloud Base](#CDP-Private-Cloud-Base)

**Specific topics** 
-	[Cloudera Manager](#Cloudera-Manager) 
-	[CDP Installation](#CDP-Installation)
-	[Cloudera Runtime](#Cloudera-Runtime)
-	[Cluster State Management](#Cluster-State-Management)
-	[Types of hosts](#Types-of-hosts)
-	[Multiple Cluster Management](#Multiple-Cluster-Management)
-	[Add a cluster](#Add-a-cluster)
-	[Usage of Provisionig Tools](#Usage-of-Provisionig-Tools)
-	[Ansible](#Ansible)
-	[Configuration Settings](#Configuration-Settings)
-	[Configuration Levels](#Configuration-Levels)
-	[Cluster Configuration](#Cluster-Configuration)


**Legal**
-	[References](#References) 
-	[Disclaimer](#Disclaimer)
-	[License](#License)

Cloudera Data Platform
--------------------------

"Cloudera Data Platform (CDP) is a hybrid data platform designed for unmatched freedom to choose—any cloud, any analytics, any data.
CDP delivers faster and easier data management and data analytics for data anywhere, with optimal performance, scalability, and security.
With CDP you get the value of CDP Private Cloud and CDP Public Cloud for faster time to value and increased IT control." ([Cloudera](https://www.cloudera.com/products/cloudera-data-platform.html))

In this guide we are focusing in CDP Private Cloud only.  But in cloudera docs you can find information about Public Cloud.


CDP Private Cloud Base
--------------------------

It is an on-premises version of Cloudera Data Platform.  This product is the result of the Cloudera Enterprise Data Hub and Hortonworks Data Platform (HDP) combination along with some new features and improvements.  

When installing a CDP Private Cloud Base cluster, you install a single parcel called Cloudera Runtime that contains all of the components. For a complete list of the included components, see [Cloudera Runtime Component Versions](https://docs.cloudera.com/cdp-private-cloud-base/7.1.8/runtime-release-notes/topics/rt-pvc-runtime-component-versions.html).

In addition to the Cloudera Runtime components, CDP Private Cloud Base includes powerful tools to help manage, govern, and secure your cluster, like Apache Atlas, Apache Ranger, Apache Spark, Apache Zookeeper, etc.  CDP also includes a powerful tool to manage one or more clusters and their configuration, and also, monitor cluster performance of the clusters and their services. This tool is called Cloudera Manager.

Cloudera Manager
--------------------

As mentioned before, this tools is used to manage the clusters and their services, but you can also use Cloudera Manager to execute installations, upgrades, maintanance workflows, encryption, access controls, and replication.

In other words, It is a web application used by administrators to:

-	Add a cluster (s)
-	Start and stop the cluster
-	Start and stop services
-	Manage hosts
-	Manage cluster resources
-	Monitor cluster (s)
-	Configure cluster (s)
-	Manage users and security 
-	Upgrade the cluster

### Before installing Cloudera Manager

**Pre-install consideratons**

-	Create a plan for storage space.  This plan should consider logs, configuration files and data to be stored in HDFS.
-	Configure network names.  This must be configure in DNS and /etc/hosts to a better performance.
-	Disabled firewall for each host in the cluster
-	Temporarily disable SE Linux
-	Enable NTP service.  Not configuring this step might cause several sincronization problems.
-	Configure parcel repositories.  This can be local or remote repositories, it depends if you have a temporal or permanent internet access.

**Configuration Terminology**

-	**Service:**  A set of related components providing a type of hadoop functionality on a cluster.  Examples: YARN, Spark, Hive, etc.

-	**Role:**  An individual component of a service.  Examples: HDFS NameNode, HDFS DataNode, etc.

-	**Role Instance:**  Would be a daemon that runs on a specific host.  For example, a DataNode daemon running on a specific host would be an instance of that role.  For gateway roles, there's no daemon running but usually there's a set of client files or configuration files that are available on those nodes.

-	**Role Group:**  It is a set of roles distributed across multiple hosts with the same configuration.  Example:  A set of DataNode roles with default settings (the same configuration).  Role groups are designed to make configuration management a little bit easier and also we can create our own role group as needed.


CDP Installation
--------------------

**Configure repositories**

We are going to need to configure a local or public repository, and it will be saved at */etc/yum.repos.d/.  Repositories for Cloudera Manager (CM) and CDP Runtime are necessary.  Also, we need to have an active subscription of our Operating System to update and install some dependencies.

**Install JDK**

The Java Development Kit (JDK) is a distribution of Java Technology by Oracle Corporation. It implements the Java Language Specification (JLS) and the Java Virtual Machine Specification (JVMS) and provides the Standard Edition (SE) of the Java Application Programming Interface (API). It is derivative of the community driven OpenJDK which Oracle stewards. It provides software for working with Java applications. [Wikipedia](https://en.wikipedia.org/wiki/Java_Development_Kit)

We are going to use Java applications during the installation, for this reason it is extreamly important to install JDK.  We can install it manually or let the Cloudera Manager Wizard install it for us.  In any case, it is importat to remember that we need to install it on all cluster hosts.

-	**Supported JDKs for CDP Private Cloud Base 7.1.x**
	-	OpenJDK 1.8
	-	OpenJDK 11
	-	Oracle JDK 1.8

-	**Requirements** 
	-	It must be 64 bits
	-	The same version on each host
	-	Must be installed at */usr/java/jdk-version*

**Enable Auto-TLS (Recommended)**

Transport Layer Security (TLS) is a cryptographic protocol designed to provide communications security over a computer network. [Wikipedia](https://en.wikipedia.org/wiki/Transport_Layer_Security)

This protocol gives you security over our cluster, e.g., avoid a malicious host installing a Cloudera Manager Agent and joining to our cluster.

We can configure TLS manually using your certificate authority or automatically with Auto-TLS (Recommended by Cloudera).

-	**Benefits of Auto-TLS**
	-	Auto-TLS automates the creation of an internal certificate authority (CA).
	-	All hosts and services will automatically have TLS configured and enabled.	

**Install Cloudera Manager**

Ones we have the repositories ready, we proceed to install CM.  Cloudera Manaager (CM) is installed on the Cloudera Manager Server host.  This is an example of the command using RHEL as OS.

```
sudo yum install cloudera-manager-daemons cloudera-manager-agent cloudera-manager-server
```

**Install and configure Databases**

We are going to need internal or external databases to store the metadata of these services:

-	CM Server
-	Oozie Server
-	Sqoop Server
-	Reports Manager
-	Hive Metastore Server
-	Hue Server
-	Ranger
-	Schema Registry
-	Streams Messaging Manager

	**Command to setup CM Database**
	
```
sudo yum install cloudera-manager-daemons cloudera-manager-agent cloudera-manager-server
```

**Install CDP Runtime and other software**

In this step we are going to need CDP Runtime and parcels to install the services to be used in our cluster.


**Set up a cluster using the wizard**

The wizard is going to guide us through all the installation process.  It's very friendly and easy to use.


Cloudera Runtime
---------------------

Cloudera Runtime is the core open-source software distribution within CDP that Cloudera maintains, supports, versions, and packages as a single entity. Cloudera Runtime includes multiple open-source projects, including Apache components, connectors and encryption components, and other components from Cloudera. These components constitute the core distribution of data management tools within CDP.  [Dell](https://infohub.delltechnologies.com/l/white-paper-data-management-with-cloudera-data-platform-on-dell-infrastructure-1/cdp-private-cloud-base-components-3)

-	**Does not include:**
	-	Cloud services like Data Hub, DWX and MLX
	-	Management Console, Workload Manager and Replication Manager
	-	Data Catalog
	-	Add-on products such as CDSW, CDF, Cloudera DataFlow, etc.

-	**What CDP includes "out of the box"?**

	| Component	| Description	|
	| ---------------	| ----------------	|
	| Apache Hadoop    			| Distributed batch processing of large datasets       				| 
	| Apache HBase   			| NoSQL database, sits on top of HDFS (Hadoop Distributed File System) so it gains the fault tolerance HDFS gives it, but is for structured storage of very large tables	|
	| Apache Hive				| Is the data warehouse, summarization and had-hoc querying tool		|
	| Hive Metastore (HMS)		| It is the metadata information for hive/impala tables				|
	| Apache Oozie				| A workflow scheduler										|
	| Apache Parquet			| Columnar storage format	|
	| Apache Spark				| Compute engine used for ETL, ML and stream processing	|
	| Apache Sqoop	| Is the way for us to pull data out of structure data sources like database management systems (Oracle, MySQL, etc) and bring that data from those sources into our cluster	|
	| YARN	| Job scheduling and cluster resource management	|
	| Apache Zookeeper	| Coordination service for distributed applications	|
	| Apache Atlas		| Metadata Management and governance and data catalog	|
	| Apache Phoenix	| OLTP, a real SQL access of large data	|
	| Apache Ranger	| Manage security on our data	|
	| Apache ORC		| Columnar storage format for hadoop	|
	| Apache Tez		| The framework for running hive queries	|
	| Apache Avro		| Data serialization system			|
	| Hue			| SQL workbench for data warehouses	|
	| Apache Impala	| Distributed MPP SQL engine, very fast engine for data	|
	| Apache Kudu		| The column oriented data store	|
	| Apache Solr		| Enterprise search platform	|
	| Apache Kafka		| A real time streaming data pipelines and applications	|


[Back to top :arrow_up:](#table-of-contents)

Cluster State Management
-----------------------------

The CM Server maintains the state of the cluster in words of two categories; *Model and Runtime*.  This information is stored in the CM Server Database.

**Model State**

This is how the cluster is supposed to run, where and what configuration is supposed to run within.  For example, if you have a cluster with 15 hosts and each one run datanode daemon.  When you update a configuration, you are updating the model state.

**Runtime State**

It captures the processes, where and what commands are currently running.  The Runtime includes the exact configuration files needed to run a process.


Types of hosts
-----------------

There are three types of nodes; Master, Worker and Gateway hosts.

**Master Hosts**

These hosts exist for roles that coordinate or manage a specific service on our cluster.  For example:

-	HDFS NameNode
-	YARN ResourceManager
-	Job history servers
-	Zookeeper 

**Worker Hosts**

These are for roles that do the distributed work for a specific service.  The following are examples of some typical service roles.

- 	HDFS DataNode
-	YARN NodeManager
-	Impala Daemons

**Gateway hosts**

These kind of hosts *do not run daemons*, but they do have information needed to provide some kind of service, for example, they can act as a gateway and the gateway role basically allows people outside the cluster to access the cluster itself.

These clusters are sometimes referred to as *edge nodes* or *edge hosts*.

Some typical roles are:

-	HDFS gateway
-	YARN gateway
-	Hive gateway
-	Spark2 gateway
-	sqoop
-	Hue server
-	HiveServer2

Multiple Cluster Management
--------------------------------

We can have one instance of Cloudera Manager Private Cloud and manage multiple clusters with it.


Add a cluster
---------------

As we mentioned before, we can add multiple clusters using our same CM instance.  When adding a cluster we are going to need this following information.

-	Cluster Name
-	Cluster type	
	-	CM will ask for this when we are adding a 2nd, 3th and subsquent cluster
	-	Our first cluster is going to be *Regular* type by default and we do not have a choice here.
	
**Cluster types**

After the first cluster we can also do a **regular cluster** which has storage nodes and compute nodes and all the services available, or we can install a **compute cluster** which consists of only the compute nodes.  In this case you would connect to some kind of existing storage, existing metadata, existing security services, so that compute cluster would only be responsible for computation which means we can tune the cluster just for that one service.

Usage of Provisionig Tools
-----------------------------

Managing the provisioning of servers can be very costly, for this reason we usually use a product like ansible that helps with automate provisioning, configuration management, and application deployment.

Ansible has the advantage to be an open-source tool.

Ansible
--------

Ansible is an open source community project sponsored by Red Hat, it's the simplest way to automate IT. Ansible is the only automation language that can be used across entire IT teams from systems and network administrators to developers and managers [ansible.com](https://www.ansible.com).

Here are some key point of Ansible:
-	It is NOT a server-agent architecture, everything works through ssh.
-	It works through JSON files and can therefore be written in any programming language.
-	It is constructed into roles, playbooks and tasks.
-	Ansible can also use YAML files to ensure flexibility and modular code development.
-	With CDP, Ansible provides a fully end-to-end, production ready deployment
	-	It installs the requiere OS packages and configs
	-	Installs and prepares supporting infrastructures (Databases, Kerberos, TLS, etc)
	-	Deploys CDP Private Coud Base clusters
	-	Enables security, encryption and High Availability (HA)
	-	Schedules CDP to spin up or down data hubs and experiences
	-	Adds local config, datasets and apps
	
As you can see, it can REALLY automates our implementation.


Configuration Settings
------------------------

Cloudera actually auto-configs some initial values for the *role groups* when we create a cluster.  They may not be the Apache default values though may override any of these values.

Configuration Levels
----------------------

We can override initial property settings and can be set at different levels as follow.

-	Service
-	Role group
-	Role instance

The settings are *inherited* from higher levels and the order of priority goes from lowest to highest, like this:  Service -> Role group -> Role instance

It means that anything set at the service is inherited by the *Role Group*, and *Role Instance* settings override *Role Group* and *Service* settings.

Cluster Configuration
-----------------------

There are over 1,800 cluster and service properties that can be configured.  Hidden properties use the cloudera default value that is set within the service parcel or package JAR File.

**Locating a configuration property**

They ways to find a property in the Cloudra Manager are:

-	Writing it on the global search box
-	Search box on a specific service's config page.

Take note that the blue arrow indicates the current value is not the default.

**Stale configuration**

When there's a change on the configuration of any service.  That change needs to be pushed out to the nodes in the cluster that it applies to, for this reason a modified configuration may require one or both of the following actions:

-	Client redeployment
-	Role instance restart or refresh

**Advanced configuration snippets (safety values)**

We can use this values to define additonal configurations.  Maybe there is a specify a value and the property does not exit in the service configuration, in that case we create an *advanced configuration snippet* and we finally overide setting for properties not exposed in Cloudra Manager.

**The Cloudera Manager API**

This is used to manage the cluster programmaticaly.  We can deploy a cluster, configure, monitor start and stop services, configure HA and more.

Here are some consideration to use the API:

-	Access using curl or included client libraries
-	Python or Java clients are recommended
-	There is a Swagger UI provided for this API
-	The API accepts HTTP POST, GET, PUT and DELETE methods. It accepts and returns JSON formatted data

We can use the API to automate cluster operations such as:

-	Obtain configuration files
-	Back up or restore the CM configuration
-	Automate different process within our cluster
-	Import/Export CM configuration

**Configuration Files on Cluster hosts**

Cloudera Manager deploys configuration settings to the Agents and they are responsible for deploying the configuration settings.  The settings ara saved to local files but before this, the agent pulls daemon configuration settings from the Cloudera Server.  It is important to remember that these settings apply to service daemons like YARN Resource Manager, NameNode or DataNode.

The client settings are used by client application and command line tools to access cluster services.  These clients typically run on gateway nodes.

Service and client configuration settings are stored seperately and each daemon has a seperate configuration file.

Service configuration settings apply to a daemon that is running, so it undestand the configuration setting needed on that machine for that daemon to run.

The default location for service daemon configuration files is */var/run/cloudera-scm-agent/process/*.

**Client configuration files**

Cloudera Manager creates client files with settings needed to access cluster services.  Those are things that are needed for the client to access the cluster, which is what our gateways do, they access to the cluster.

The client configuration files are generated by Cloudera Manager when:
	-	A cluster is created
	-	A service or a gateway role is added on a host.

A gateway role includes client configuration, libraries, and binaries, but no daemons.  This is a very important thing to remember.

**Cluster-wide configurations**

Review or modify setting, including:
	-	Non-default value configuration setting
	-	Log directories
	-	Disk space thresholds
	-	Advanced configuration snippets

 


References
-------------
[docs.cloudera.com](https://docs.cloudera.com) \
[infohub.delltechnologies.com](https://infohub.delltechnologies.com)

Disclaimer
------------
The author of this content cannot guarantee the validity of the information found here. Please make sure that you understand that the information provided here is being provided freely, and that no kind of agreement or contract is created between you and any persons associated with this content or project. The authors and contributors do not assume and hereby disclaim any liability to any party for any loss, damage, or disruption caused by errors or omissions in the information contained in, associated with, or linked from this content, whether such errors or omissions result from negligence, accident, or any other cause.

License
---------
<a rel="license" href="http://creativecommons.org/licenses/by/4.0/"><img alt="Creative Commons License" style="border-width:0" src="https://i.creativecommons.org/l/by/4.0/88x31.png" /></a><br />This work is licensed under a <a rel="license" href="http://creativecommons.org/licenses/by/4.0/">Creative Commons Attribution 4.0 International License</a>.
