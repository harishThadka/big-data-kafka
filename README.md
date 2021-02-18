# big-data-kafka

## What is kafka?🙄🙄🤔
- Apache Kafka is an open-source stream-processing software platform developed by the Apache Software Foundation, written in Scala and Java.
- https://techbeacon.com/app-dev-testing/what-apache-kafka-why-it-so-popular-should-you-use-it
- https://www.youtube.com/watch?v=_q1IjK5jjyU&ab_channel=StephaneMaarek
## What is Zookeeper?🤔🤔🤔
- Apache ZooKeeper is an open-source server for highly reliable distributed coordination of cloud applications. It is a project of the Apache Software Foundation.
- https://www.cloudkarafka.com/blog/2018-07-04-cloudkarafka_what_is_zookeeper.html

## Kafka Installation and Setup:🤗

### Prerequisites:
- maven
- openjdk

### Installation: (kafka with zookeeper)
- Download latest version kafka from this [link](https://kafka.apache.org/quickstart)
- Put the .tgz file in C:\ folder
- Un-tar it (using Bash) and change into the directory.  The $ indicates a Bash prompt.
```
tar -xzf <filename>
cd <folder>
```
- It should contain below files
    1. bin
    1. bin/windows
    1. config (view some of the properties files)
    1. libs
### Setup environment variables:
- Windows + Edit the System Environment Variables / Environment Variables / System variables (bottom half). Note:  Use the version you installed in the following. 
    1. JAVA_HOME = C:\Program Files\OpenJDK\jdk-version folder
    1. KAFKA_HOME =  C:\kafka-version folder
    1. M2_HOME = C:\ProgramData\chocolatey\lib\maven\apache-maven-version
- Path - must include (make sure you have only one JDK location in your path!)
1. %JAVA_HOME%\bin OR C:\Program Files\OpenJDK\jdk-version\bin (or similar, NOT both!)
1. %M2_HOME%\bin
1. %KAFKA_HOME%\bin
1. %KAFKA_HOME%\bin\windows

## Running server
## Issues:
```
The system cannot find the path specified
```
Resolve: https://stackoverflow.com/questions/51120971/running-kafka-on-windows-10-fails-the-system-cannot-find-the-path-specified