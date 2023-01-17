# Cloudera CDP Administrator Private Cloud Base
This is a study guide I built while studying to get CDP Administrator  Private Cloud Base (CDP-2001) certification.  I wish it helps to someone interested while having a good time as I did.

This guide has all the documentation needed to achieve the CDP Administrator Private Cloude Base (CDP-2001) Certification, and at the same time it gives you the oportunity to learn all the tecnologies needed to manage a CDP Cluster efficiency following best practices and recommendations from Cloudera.

## Content
[Cloudera Data Platform](./sas/1.Cloudera%20Data%20Platform.md) 
[CDP Private Cloud Base](#CDP Private Cloud Base) \
[Cloudera Manager](#Cloudera Manager) \
[References](#References) \

#### CDP Private Cloud Base
It is an on-premises version of Cloudera Data Platform.  This product is the result of the Cloudera Enterprise Data Hub and Hortonworks Data Platform (HDP) combination along with some new features and improvements.  

When installing a CDP Private Cloud Base cluster, you install a single parcel called Cloudera Runtime that contains all of the components. For a complete list of the included components, see [Cloudera Runtime Component Versions](https://docs.cloudera.com/cdp-private-cloud-base/7.1.8/runtime-release-notes/topics/rt-pvc-runtime-component-versions.html) Cloudera Runtime Component Versions.

In addition to the Cloudera Runtime components, CDP Private Cloud Base includes powerful tools to help manage, govern, and secure your cluster, like Apache Atlas, Apache Ranger, Apache Spark, Apache Zookeeper, etc.  CDP also includes a powerful tool to manage one or more clusters and their configuration, and also, monitor cluster performance of the clusters and their services. This tool is called Cloudera Manager.

#### Cloudera Manager
As mentioned before, this tools is used to manage the clusters and their services, but you can also use Cloudera Manager to manage installations, upgrades, maintanance workflows, encryption, access controls, and replication.

#### Before installing Cloudera Manager
**- Pre-install consideratons**
	- Create a plan for storage space.  This plan should consider logs, configuration files and data to be stored in HDFS.
	- Configure network names.  This must be configure in DNS and /etc/hosts to a better performance.
	- Disabled firewall for each host in the cluster
	- Temporarily disable SE Linux
	- Enable NTP service.  Not configuring this step might cause several sincronization problems.
	- Configure parcel repositories.  This can be local or remote repositories.

#### References
[docs.cloudera.com](https://docs.cloudera.com) 


