## Table of Contents

 

### OVERVIEW

 

- About Aerospike App for Splunk

- Release notes

- Performance benchmarks

- Support and resources

 

### INSTALLATION

 

- Hardware and software requirements

- Installation steps

- Deploy to single server instance

- Deploy to distributed deployment

- Deploy to distributed deployment with Search Head Pooling

- Deploy to distributed deployment with Search Head Clustering

- Deploy to Splunk Cloud

 

 

### USER GUIDE

 

- Key concepts

- Data types

- Lookups

- Configure Aerospike App for Splunk

- Troubleshooting

- Upgrade

- Example Use Case-based Scenario

 

---

### OVERVIEW

 

#### About the Aerospike App for Splunk

 

| Author | Sachin Lokulwar, GSLab |
| ------ | ---------------------- |
| App Version | 1.0 |
| Vendor Products | Aerospike  |
| Has index-time operations | false |
| Create an index | true |
| Implements summarization | false |

 

The Aerospike App for Splunk allows Splunk® Enterprise administrator to monitor Aerospike Cluster.

Aerospike App for Splunk can collect run-time statistics from every node within the Aerospike cluster.

This app provides general health monitoring reports, statistics, dashboards and alerts for Aerospike Clusters.

 

##### Scripts and binaries

 

| Script | Purpose |
| ------ | ------- |
| citrusleaf.py | Aerospike’s native library that provisions statistics for Nodes, Namespace, Latency and XDR |
| controller.py | controller for reading statistics from citrusleaf.py |
| aerospike.py | Gets total statistics of Aerospike cluster (for e.g.; Nodes statistics, Namespace statistics and so on) |
| statistics.py | Gets complete statistics of all nodes present in Aerospike cluster |
| latency.py | Gets All latency information about all the connected nodes within that cluster|
| namespace.py | Gets node wise statistics of all namespaces present within the Aerospike cluster |
| xdr.py | Gets all XDR statistics of nodes present within Aerospike cluster |

 

#### Release notes

 

##### About this release

 

Version 1.0 of the Aerospike App for Splunk is compatible with:

 

| Splunk Enterprise versions | 6.2.3 |
| -------------------------- | ----- |
| CIM | NA |
| Platforms | Supports Linux, Unix, CentOS, Ubuntu, Debian, Windows 7 & 8|
| Vendor Products | NA |
| Lookup file changes | NA |

 

##### New features

 

Aerospike App for Splunk includes following new features:

 

- Not Applicable.

 

##### Fixed issues

 

- Not Applicable.

 

##### Known issues

 

- Version 1.0 of the Aerospike App for Splunk has no known issues.

 

##### Third-party software attributions

 

- Not Applicable

 

#### Performance benchmarks

 

- Not Applicable

 

##### Support and resources

 

**Questions and answers**

 

- Not Applicable

 

**Support**

 

Report issues to splunk@gslab.com.

Hours of operations: 9 hours a day (04:30 - 13:30 UTC).

Saturday and Sunday are weekly offs.

Response time, user should expect when they report an issue: within 12 hours.

Initially, issues will be tracked using the email thread. If the issue is found to be a valid bug, it will be moved to a bug tracking system.

 

 

## INSTALLATION AND CONFIGURATION

 

### Hardware and software requirements

 

#### Hardware requirements

 

Aerospike App for Splunk supports the following server platforms in the versions supported by Splunk Enterprise:

 

- Linux, Unix, CentOS, Ubuntu and Debian

- Windows 7 and 8

 

#### Software requirements

 

To function properly, Splunk App for Aerospike requires the following software:

- Python 2.7

 

#### Splunk Enterprise system requirements

 

This app runs on Splunk Enterprise version as a result this app is available for Splunk Enterprise users only and it runs within the Splunk Enterprise monitoring system Splunk system requirements are can be seen on (http://docs.splunk.com/Documentation/Splunk/latest/Installation/Systemrequirements).

 

#### Download

 

Download the Aerospike App for Splunk from Splunkbase.

 

#### Installation steps

 

To install and configure this app on your supported platform, follow these steps:

 

1. Make sure that Splunk (6.2.3 or above) is running.

2. Login to Splunk with Administrator credentials.

3. Go to the Apps tab.

4. Go to 'Browse more apps' page.

5. Search for 'Aerospike App for Splunk'.

6. Click on the 'Install' button.

7. Stop the Splunk server by running $SPLUNK_HOME/bin/splunk stop.

8. Start the Splunk server again by running $SPLUNK_HOME/bin/splunk start.

9. Access the Aerospike App for Splunk from Apps list. If you are doing this for the first time, you will see a Setup page.

10. On the Setup page, enter valid Node Address of any node from aerospike cluster and click on 'Save'.

 

##### Deploy to single server instance

 

Follow these steps to install the app in a single server instance of Splunk Enterprise:

 

- Not Applicable.

 

##### Deploy to distributed deployment

 

**Install to search head**

 

- Not Applicable.

 

**Install to indexers**

 

- Not Applicable.

 

**Install to forwarders**

 

- Not Applicable.

 

##### Deploy to distributed deployment with Search Head Pooling

- Not Applicable.

 

##### Deploy to distributed deployment with Search Head Clustering

- Not Applicable.

 

##### Deploy to Splunk Cloud

- Not Applicable.

 

## USER GUIDE

 

### Key concepts for Splunk App for Aerospike

 

- On launching this app for first time, it redirects the user to setup page. From setup page you can provide IP address of any connected nodes present within the aerospike cluster. This seed node acts as a gateway for getting all Aerospike statistics.

 

-What is in the app:

| Location | Description |
| -------- | ----------- |
| Homepage | Shows some important charts generated from aerospike statistics like Memory Usage, Disk Usage, Reads per second(RPS), Writes per second(WPS), Connected nodes, Namespaces etc. Additionally it also shows the latency charts of all connected nodes within the cluster |
| Statistics | Shows all statistics related to Aerospike Nodes, Namespaces and Cross Datacenter replication also commonly known as XDR |
| Setup | Allows the user to change the monitoring of a cluster to a different cluster by provisioning the IP address of any connected node within that cluster |
| Search | Allows the user to search any current or historical statistics generated by aerospike |
| Alerts | Here we provide some predefined alerts like Memory Usage, Disk Usage ect. User can create custom alerts by selecting search option present on menu bar |
| Dashboards | Here the user can create/define their own dashboards.  At first this section is empty allowing any user to create custom dashboards by selecting the search option |

 

### Data types

This app provides the index-time and search-time information for the following types of data from Aerospike.

 

**Data type**

 

- Sourcetype = Aerospike

                It provides key statistics of Aerospike cluster, Nodes and Namespace.

 

- Sourcetype = Aerospike_statistics

                It provides all statistics of every node present within the aerospike cluster.

 

- Sourcetype = Aerospike_namespace

                It provides node wise namespace statistics within the aerospike cluster.

               

- Sourcetype = Aerospike_latency

                It provides latency stats of all connected nodes within that cluster.

               

- Sourcetype = Aerospike_xdr

                It provides XDR statistics of all nodes present within the aerospike cluster.

 

These data types support the following Common Information Data Model:

 

- Not Applicable.

 

### Lookups

 

Aerospike App for Splunk contains 0 lookup files.

 

** Lookupname**

 

- Not Applicable.

 

### Configure Aerospike App for Splunk

 

 - When you access Aerospike App for Splunk, make sure that you provide correct node address which is present within Aerospike cluster.

 - In order to update this node address, go to the 'Setup' link on the menu bar inside the app and change the node IP address in order to monitor a different cluster.

 

### Troubleshoot Aerospike App for Splunk

 

***Problem***

Aerospike Cluster monitoring information is not displayed on home page

***Cause***

The node address provided may not be running or does not have Aerospike setup on it.

***Resolution***

- Go to setup link present on your menu bar and change the seed node IP address to where the Aerospike is setup.

 

### Upgrade Splunk App for Aerospike

- Not Applicable.

 

### Example Use Case ###

Aerospike App for Splunk is designed for Aerospike users that have already purchased Splunk Enterprise version and would like to monitor Aerospike stats within the same monitoring console.

Aerospike’s statistics, throughput and latency information can be tracked using this application. This application uses Splunk’s native data storage that allows the users to view historical statistics.

 

 

Start and configure Aerospike App for Splunk:

1. Make sure that Splunk (6.2.3 or above) is running.

2. Login to Splunk with Administrator credentials.

3. Go to the Apps tab.

4. Go to 'Browse more apps' page.

5. Search for 'Aerospike App for Splunk'.

6. Click on the 'Install' button.

7. Stop the Splunk server by running $SPLUNK_HOME/bin/splunk stop.

8. Start the Splunk server again by running $SPLUNK_HOME/bin/splunk start.

9. Access the Aerospike App for Splunk from Apps list. If you are doing this for the first time, you will see a Setup page.

10. On the Setup page, enter valid Node Address of any node from aerospike cluster and click on 'Save'.