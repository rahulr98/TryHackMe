## KIBANA (KIBA)

TASK 1 - FLAGS

QUESTION 1-

![image](https://github.com/rahulr98/TryHackMe/assets/116432525/176d9867-bd41-44e4-a973-4486f521aba4)

QUESTION 2-

![image](https://github.com/rahulr98/TryHackMe/assets/116432525/38175a23-f58f-4015-be6a-35bfaeecf477)

QUESTION 3-

CVE of kibana version 6.5.4 = CVE-2019-7609

> Source internet.

![image](https://github.com/rahulr98/TryHackMe/assets/116432525/c54ba665-8fa5-4dca-a3f9-5c38042292ee)

QUESTION 4-

ANS-  `THM{1s_easy_pwn3d_k1bana_w1th_rce}`
 
  - Exploit CVE-2019-7609(kibana RCE) on right way by python2 scripts
 
> Reverse shell completed by targetting 10.10.185.60:5601 for attack the kiba server and accessing the user privilege for getting *user.txt*.

![image](https://github.com/rahulr98/TryHackMe/assets/116432525/47986c12-ff59-4f67-ac10-5483f0f28218)

![image](https://github.com/rahulr98/TryHackMe/assets/116432525/0a354366-1965-429c-8dbe-aab13f39da7f)

QUESTION 5-

![image](https://github.com/rahulr98/TryHackMe/assets/116432525/002043e5-b84e-4ad2-b17e-25fdbd5294fc)

QUESTION 6-

  - First tried to find what are the queried files are available using `getcap -r / 2>/dev/null`.
  - We confirmed `/home/kiba/.hackmeplease/python3 = cap_setuid+ep` has a vulnerability to exploit/access the root privilege.
 
![image](https://github.com/rahulr98/TryHackMe/assets/116432525/86ecb3b0-12dd-4a16-ae49-5b5f6eb397e0)

  - After running the shell script `/home/kiba/.hackmeplease/python3 -c 'import os; os.setuid(0); os.system("/bin/sh")'` we got the root privilege and able to find the *root.txt* file

![image](https://github.com/rahulr98/TryHackMe/assets/116432525/40ad31c4-ab84-4ee3-8cee-2fc7bf5d2d3b)
