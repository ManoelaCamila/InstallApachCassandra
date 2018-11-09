# Install Apache Cassandra on Ubuntu 16.04

Script to install Apache Cassandra on Ubuntu 16.4

## Getting Started

Cassandra, or Apache Cassandra, is a highly scalable open source NoSQL database system, achieving great performance on multi-node setups.

In this tutorial, you’ll learn how to install and use it to run a single-node cluster on Ubuntu 16.04.

### Prerequisites

To complete this tutorial, you will need the following:

* Ubuntu 16.04
* A non-root user with sudo privileges

## Installing

### Installing the Oracle Java Virtual Machine

Cassandra requires that the Oracle Java SE Runtime Environment (JRE) be installed. So, in this step, you'll install and verify that it's the default JRE.

To make the Oracle JRE package available, you'll have to add a Personal Package Archives (PPA) using this command:

```
$ sudo add-apt-repository ppa:webupd8team/java
```

Update the package database:

```
$ sudo apt-get update
```

Then install the Oracle JRE. Installing this particular package not only installs it but also makes it the default JRE. When prompted, accept the license agreement:

```
$ sudo apt-get install oracle-java8-set-default
```

After installing it, verify that it's now the default JRE:

```
$ java -version
```

You should see output similar to the following:

```
java version "1.8.0_60"
Java(TM) SE Runtime Environment (build 1.8.0_60-b27)
Java HotSpot(TM) 64-Bit Server VM (build 25.60-b23, mixed mode)
```

### Installing Apache Cassandra

To install Apache Cassandra on your server, first you need to add the Cassandra repository. At the moment of writing this tutorial, the latest stable release of Cassandra is 3.11.0 Therefore, run the following command to add the Cassandra repository on your server:

```
$ echo "deb http://www.apache.org/dist/cassandra/debian 311x main" | sudo tee -a /etc/apt/sources.list.d/cassandra.sources.list
```

Next, add the Cassandra repository keys:

```
$ curl https://www.apache.org/dist/cassandra/KEYS | sudo apt-key add -
$ sudo apt-key adv --keyserver pool.sks-keyservers.net --recv-key A278B781FE4B2BDA
```

Update the package index:

```
$ sudo apt-get update
```

Finally, install Apache Cassandra using the following command:

```
$ sudo apt-get install cassandra
```

### Using Apache Cassandra

To open the command shell of cassandra you can use the following command:

```
$ cqlsh
```

#### Start, Stop and Enable Apache Cassandra

To start the Apache Cassandra service on your server, you can use the following command:

```
$ sudo systemctl start cassandra.service
```

To stop the service, you can use the command below:

```
$ sudo systemctl stop cassandra.service
```

If the service is not already enabled on system boot, you can enable it by using the command below:

```
$ sudo systemctl enable cassandra.service
```
