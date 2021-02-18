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

- Use a different PowerShell as Administrator window for each process.  You may minimize windows, but they must remain  open to keep the processes running.
These assume execution of commands from your %KAFKA_HOME% folder (e.g., C:\kafka-version) adjust them as needed. 
These commands are long - create a text file or build a Markdown file in GitHub to store them for reference. You must provide your custom commands in your unique submission.  
1. Window 1 - Run Zookeeper Service  (keep window open)

```
.\bin\windows\zookeeper-server-start.bat .\config\zookeeper.properties
```
Window 2 - Run Kafka Service (keep window open)

```
.\bin\windows\kafka-server-start.bat .\config\server.properties
```
Window 3 (temporary) - Execute One-Time Commands - create, list, delete topics 

```
.\bin\windows\kafka-topics.bat --zookeeper localhost:2181
 --replication-factor 1 --partitions 1 --create --topic bearcat-messages
.\bin\windows\kafka-topics.bat --zookeeper localhost:2181 --list
```
Window 4 - Run Kafka Producer (will provide a > prompt for writing messages)

```
.\bin\windows\kafka-console-producer.bat --broker-list localhost:9092 --topic bearcat-messages
```
Window 5 - Run Kafka Consumer (to show messages from the beginning)

```
.\bin\windows\kafka-console-consumer.bat --bootstrap-server localhost:9092 --topic bearcat-messages --from-beginning
```
## Issues:

### #Issue 1:
```
The system cannot find the path specified
```
Resolve: https://stackoverflow.com/questions/51120971/running-kafka-on-windows-10-fails-the-system-cannot-find-the-path-specified