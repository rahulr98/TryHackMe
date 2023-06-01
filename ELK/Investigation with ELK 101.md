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
 
QUESTION 1-
  
 ![1](https://github.com/rahulr98/TryHackMe/assets/116432525/ec48b1ce-312b-4567-9e74-f74a523846b1)

QUESTION 2-

![2](https://github.com/rahulr98/TryHackMe/assets/116432525/a0809862-5555-4a1c-982d-2e46d4c89f8c)

QUESTION 3-

![3](https://github.com/rahulr98/TryHackMe/assets/116432525/4ca70b3b-77b5-4c84-ab3a-25cf5a8d1c1d)

QUESTION 4-

![4](https://github.com/rahulr98/TryHackMe/assets/116432525/3c4c597f-39b2-4ae9-9a4b-ab35562b4ef9)

QUESTION 5-

![5](https://github.com/rahulr98/TryHackMe/assets/116432525/ef059241-2ed0-4917-8ff2-e65ce4002e7d)

QUESTION 6-

![6](https://github.com/rahulr98/TryHackMe/assets/116432525/65624bba-8504-45b1-ae6c-5bf16666f168)

QUESTION 7-

![7](https://github.com/rahulr98/TryHackMe/assets/116432525/8526ceae-63b0-4940-a169-0cd10adc88bb)

### TASK 6 - KQL Overview

QUESTION 1-

![8](https://github.com/rahulr98/TryHackMe/assets/116432525/0aa5d8df-ccc1-4962-96f2-a6275071f277)

QUESTION 2-

![9](https://github.com/rahulr98/TryHackMe/assets/116432525/e8dfdfe9-4f62-4ce3-be8e-6b447d25e59f)

### TASK 7 - Creating Visualizations

QUESTION 1-

![10](https://github.com/rahulr98/TryHackMe/assets/116432525/d9a25562-6665-48a2-a66e-d663ff33c786)

QUESTION 2-

![10 (2)](https://github.com/rahulr98/TryHackMe/assets/116432525/429e56b0-940f-4894-84ea-6b6b6598f5b2)


