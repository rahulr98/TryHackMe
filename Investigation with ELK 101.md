## Investigation with ELK 101

### TASK-1  Introduction
  
  - In this room, we will learn how to utilize the Kibana interface to search, filter, and create visualizations and dashboards, while investigating VPN logs for anomalies. This room also covers a brief overview of Elasticstack components and how they work together.

### TASK-2 Incident Handling Scenario

  - A US-based company CyberT has been monitoring the VPN logs of the employees, and the SOC team detected some anomalies in the VPN activities. Our task as SOC Analysts is to examine the VPN logs for January 2022 and identify the anomalies. Some of the key points to note before the investigation are:
    - All VPN logs are being ingested into the index `vpn_connections`.
    - The index contains the VPN logs for January 2022.
    - A user `Johny Brown` was terminated on 1st January 2022.
    - We observed failed connection attempts against some users that need to be investigated.
 
### TASK-3 ElasticStack Overview
  
**Questions**

![2023-06-01_17-41](https://github.com/rahulr98/TryHackMe/assets/116432525/1d23a3c5-7256-4486-81ae-a3d6f4b897fb)
  
  - No, Logstash is a data processing engine used to take the data from different source, apply the filters on it or normalize. *Kibana* is Used to visualize the data.
  
![2023-06-01_17-41_1](https://github.com/rahulr98/TryHackMe/assets/116432525/f6815980-a2d7-436a-9758-5bbca6dca1de)

 -  Elasticstash only supports JSON format.
 
 ### TASK- 4 , 5 Discover Tab
 
 


