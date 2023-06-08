# ItsyBitsy

### TASK-1  INTRODUCTION

  In this challenge room, we will take a simple challenge to investigate an alert by IDS regarding a potential C2 communication.

![image](https://github.com/rahulr98/TryHackMe/assets/116432525/349253b7-274d-4bbb-a3af-c6b9e9055375)

### TASK-2 Scenario - Investigate a potential C2 communication alert

**Scenario**

  During normal SOC monitoring, Analyst John observed an alert on an IDS solution indicating a potential C2 communication from a user Browne from the HR department. A suspicious file was accessed containing a malicious pattern THM:{ ________ }. A week-long HTTP connection logs have been pulled to investigate. Due to limited resources, only the connection logs could be pulled out and are ingested into the connection_logs index in Kibana.

**QUESTION-1**

![image](https://github.com/rahulr98/TryHackMe/assets/116432525/20f09f7f-4102-4e93-8571-5d889aaf660e)

  - We have to adjust the *time filter* to show the events happend on *March 2022*.

> Number of events= 1482

![image](https://github.com/rahulr98/TryHackMe/assets/116432525/1c817d34-6401-4416-bb1b-478ddbd0eb28)

**QUESTION-2**

  - Check *source_ip* to view the IP addresses associated with the logs.
  - We cannot conclude that which IP is associated with the suspect user.

![image](https://github.com/rahulr98/TryHackMe/assets/116432525/0a13e544-7abe-4bff-b822-b8616bfd397b)

  - Take IP which has fewer logs, and create a filter to view logs which is a product of that IP address.

> Source_ip of suspected user - 192.166.65.54

> _index:connection_logs AND source_ip:192.166.65.54

![image](https://github.com/rahulr98/TryHackMe/assets/116432525/ac2f6374-3b6a-444b-b95f-047be926a45f)

  - To ensure if the IP is an C2C server, we can use *Alienvault's* Malware C2C database.

![image](https://github.com/rahulr98/TryHackMe/assets/116432525/bda9e915-bb14-4199-9e7b-fbb738044ef4)

  - From the search result , we can see that the IP 104.23.99.198 is present in their database hence confirming our doubt.
  - So, the *source_ip* which is associated with the suspected user is found.

![image](https://github.com/rahulr98/TryHackMe/assets/116432525/5fc5f688-0b70-4f81-8dd9-d3d23261fb1e)
--------------------------------------------------------------------------------------------------------------------------------------------------------------------
**QUESTION-3**

![image](https://github.com/rahulr98/TryHackMe/assets/116432525/47945e0e-e3f8-4311-97ab-4848dc58dad9)

  ` Query- index:connection_logs AND user_agent:bitsadmin AND destination_ip : 104.23.99.190`

  - In the Fields pane , click on user_agent field to view what user agent was used to download files.

![image](https://github.com/rahulr98/TryHackMe/assets/116432525/4c7ae2eb-33be-4bde-bb9f-344b7074b67f)
---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

**QUESTION-4**

  `Query-  index:connection_logs AND user_agent:bitsadmin AND destination_ip :104.23.99.190 AND host: *`
  
![image](https://github.com/rahulr98/TryHackMe/assets/116432525/ebced04c-0b67-45ef-b2cf-b5df04ad89c5)
