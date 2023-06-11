# SIGMA
**INTRODUCTION**

  Detection engineering is an important role and task for a security analyst. It involves developing processes that will guide you as an analyst to identify threats before they cause any harm to an environment through the use of rules. This room will introduce you to Sigma, an open-source generic signature language used to write detection rules applicable across different SIEM backends.
  
**What is Sigma ?**
 
  - Sigma is an open-source generic signature language developed by Florian Roth & Thomas Patzke to describe log events in a structured format. This allows for quick sharing of detection methods by security analysts. It is mentioned that "Sigma is for log files as Snort is for network traffic, and Yara is for files."
  - Through log monitoring and analysis, SOC analysts are tasked with collecting, analysing and extracting as much usable information from logs and using it to build detection queries and searches for their environments. However, on most occasions, it becomes challenging to standardise investigations and have the ability to share them with other analysts for detection enrichment. Sharing Indicators of compromise (IOC) and signatures may not be enough, as log events are often left unattended. Here is where Sigma seeks to bridge the gap.

**Sigma Use Cases**
  
  Sigma was developed to satisfy the following uses:
    - To make detection methods and signatures shareable alongside IOCs and Yara rules.
    - To write SIEM searches that avoid vendor lock-in.
    - To share signatures with threat intelligence communities.
    - To write custom detection rules for malicious behaviour based on specific conditions.

**Sigma Development Process**
 
 As a SOC analyst, the process of using Sigma to write up your detection rules will involve understanding the elements mentioned below:
    - Sigma Rule Format: Generic structured log descriptions written in YAML.
    - Sigma Converter: A set of python scripts that will process the rules on the backend and perform custom field matching based on specified SIEM query language.
    - Machine Query: Resulting search query to filter out alerts during investigations. The query will be based on the specified SIEM.

### TASK-3  SIGMA RULE SYNTAX

> Sigma syntax

![image](https://github.com/rahulr98/TryHackMe/assets/116432525/c8866436-35e1-4a5b-b68c-997520190545)

**QUESTION-1**

![image](https://github.com/rahulr98/TryHackMe/assets/116432525/2eb2bb18-0c70-47e4-9d80-365455cf3bba)

> *Experimental*: The rule is very generic and is being tested. It could lead to false results, be noisy, and identify interesting events.

**QUESTION-2**

![image](https://github.com/rahulr98/TryHackMe/assets/116432525/a570f399-fc32-4c65-b6f1-6c802d39ad86)

> Detection: A required field in the detection rule describes the parameters of the malicious activity we need an alert for. The parameters are divided into two main parts: the *search identifiers* - the fields and values that the detection should be searching for -  and condition expression - which sets the action to be taken on the detection

**QUESTION-3**

![image](https://github.com/rahulr98/TryHackMe/assets/116432525/cff9090d-3cf0-4e8b-8761-b1f8567b4ee8)

> The definition of the search identifiers can comprise two data structures - *lists and maps* - which dictate the order in which the detection would be processed.

### TASK-4  RULE WRITING AND CONVERSION

**QUESTION-1**

![image](https://github.com/rahulr98/TryHackMe/assets/116432525/44b8b690-aa62-487d-8189-3b3954deab41)

> **Sigmac**:
  _Sigmac_ is a Python-written tool that converts Sigma rules by matching the detection log source field values to the appropriate SIEM backend fields. As part of the Sigma repo (Advisable to clone the repo to get the tool and all the available rules published by the Sigma team), this tool allows for quick and easy conversion of Sigma rules from the command line. Below is a snippet of how to use the tool through its help command, and we shall display the basic syntax of using the tool by converting the AnyDesk rule we have written to the Splunk query.

**QUESTION-2 and 3**

> For answering 2nd and 3rd questions, we have to create _Anydesk sigma rule_ and convert it into a _Elastic Query_ for testing the log files.

  - Use _Uncode.io_ universal sigma rule converter for converting sigma rule to elastic query.

![1](https://github.com/rahulr98/TryHackMe/assets/116432525/3c32cb0d-1bab-4893-8037-0ce075afc5b0)

![2](https://github.com/rahulr98/TryHackMe/assets/116432525/68001b95-6673-4da1-a90b-657b6dc691af)

  - After converting the rules, We have to modify the elastic query with no regex charecters.
  - The copy the query and search it in Elastic.
  - We can find the _timestamp_ and the version of Anydesk.

![image](https://github.com/rahulr98/TryHackMe/assets/116432525/6c68556f-859c-4541-9c09-d0528e6383d0)

![3](https://github.com/rahulr98/TryHackMe/assets/116432525/74b25ef1-b3a1-4b00-8475-b7035e034047)

![image](https://github.com/rahulr98/TryHackMe/assets/116432525/b5305781-f504-4412-a964-23f860921e8c)

![4](https://github.com/rahulr98/TryHackMe/assets/116432525/acd89db7-b27e-4397-9098-5fa84a5c415f)


