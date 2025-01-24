
AZURE VIRTUAL MACHINES AND NETWORKING  https://github.com/RODNEYBB1/MICROSOFT-AZURE.git
----------------
DESCRIPTION
-----------------
THIS PROJECT CONSISTS OF CREATING TWO VIRTUAL MACHINES AND A NETWORK WHERE I MONITOR NETWORK TRAFFIC WITH A SOFTWARE CALLED WIRESHARK. THIS IS ALL DONE 
WITHIN MICROSOFT AZURE.
------------------

<h2>Environments and Technologies Used</h2>

-MICROSOFT AZURE
-VIRTUAL MACHINES
-REMOTE DESKTOP CONNECTION
-WIRESHARK
-VARIOUS NETWORK PROTOCOLS (ICMP,SSH,DHCP,DNS)


<h2>Operating Systems Used </h2>

- Windows 10
- UBUNTU 24.04


<h2>PROJECT WALK-THROUGH :</h2>
   =NAVIGATE TO MICROSOFT AZURE CREATE RESOURCE GROUP 

   ![image](https://github.com/user-attachments/assets/e90c011e-fde8-4ded-8230-5b4e6a0033f1)

   =ONCE MY RESOURCE GROUP IS CREATED, NEXT I CREATE THE FIRST VIRTUAL MACHINE

  ![image](https://github.com/user-attachments/assets/c40d0b96-8eda-4f1f-9d30-a816801b06f8)

  ![image](https://github.com/user-attachments/assets/ab41bb62-0e61-4a2c-a61e-3e279d50c8c6)

  I WILL LEAVE ALL OTHER SETTINGS TO DEFAULT AND CREATE THIS VM :

  ![image](https://github.com/user-attachments/assets/07e2a714-fe22-42cd-9d08-6fc72a5ef3d0)

  NOW AZURE HAS SET UP A VM, AN IP FOR THE VM, A NETWORK, DISK, AND A NETWORK INTERFACE CARD :

  ![image](https://github.com/user-attachments/assets/a5ae0fbc-892d-46ad-9663-5c1fc6bf35d8)

  =SECOND VM SETUP :

  ![image](https://github.com/user-attachments/assets/fab0914f-af39-4db1-b799-e10ccf2b0241)

  ![image](https://github.com/user-attachments/assets/d89ca2a3-146e-444d-b7e1-6470ba6825ae)

  **** BE SURE THAT BOTH VM'S ON THE SAME VIRTUAL NETWORK*****

  =NOW WE USE VM1 PUBLIC IP TO CONNECT TO IT USING REMOTE DESKTOP THEN DOWNLOAD WIRESHARK WITHIN YOUR VM
  
  ![image](https://github.com/user-attachments/assets/940874af-4721-4927-8094-0bfa19275712)

=ONCE WIRE SHARK IS DOWNLOADED AND OPEN I WILL SELECT "ETHERNET" TO OBSERVE NETWORK TRAFFIC :


![image](https://github.com/user-attachments/assets/d5178f4e-7d36-4ed6-a4f9-e1f266832901)

TO FILTER FOR (ICMP) TRAFFIC TYPE ICMP IN THE PINK SEARCH BAR ON WIRESHARK AT THE TOP. TO MAKE TRAFFIC I WILL GET THE PRIVATE IP ADDRESS OF VM2 AND PING IT FROM POWERSHELL:


![image](https://github.com/user-attachments/assets/52fef907-5d75-43cb-8ccc-b93e10e18a01)

![image](https://github.com/user-attachments/assets/5e3de84f-ef77-4242-9483-53e22ac54ebb)

=NOW CAN MAKE SOME FIREWALL CONFIGURATIONS TO DENY ANY ICMP TRAFFIC. TO DO THIS I WILL ENTER A PERPETUAL PING COMMAND INTO POWERSHELL :

![image](https://github.com/user-attachments/assets/31c6053b-b557-4c44-adab-fda5e5354ffb)

=NEXT I WILL GO TO VM2 NETWORK SECURITY GROUP AND CREATE A NEW INBOUND SECURITY RULE DENYING ALL ICMP TRAFFIC MAKING SURE TO PUT ITS PRIORTY HIGHEST, SO IT WILL TAKE PRECENCE BEFORE ANY OTHER
RULES :

![image](https://github.com/user-attachments/assets/5f1b5bc4-d417-4c81-83b9-50c49c579639)

GOING BACK TO OUR VM WE CAN SEE THAT THE ICMP ECHO REQUESTS ARE GETTING RESPONSES DUE TO THE SECURITY CHANGES :

![image](https://github.com/user-attachments/assets/827b118d-24ce-483d-9dca-17bb024f6461)

=TO REVERT THE CHANGE WE CAN EITHER SWITCH THE INBOUND RULE TO "ALLOW" INSTEAD OF "DENY" OR DELETE THE RULE :

![image](https://github.com/user-attachments/assets/3a58eac8-8173-4b03-ac59-aeccc33226fa)

=NOW ICMP ECHO REQUEST AR BACK TO GETTING RESPONSES :

![image](https://github.com/user-attachments/assets/4dd36bf4-96ca-433b-bf98-ed08754a132a)

= NOW I WILL FILTER TO ONLY SHOW SSH TRAFFIC BY TYPING SSH INTO SEARCH BAR AT THE TOP AND I WILL TYPE SSH INTO VM USING POWERSHELL :

![image](https://github.com/user-attachments/assets/eeddde9f-34bb-469a-bf1b-a52e087b17c7)

=AFTER FILTERING FOR DHCP TRAFFIC , I ATTEMPTED TO GET A NEW IP ADDRESS BY USING THE IPCONFIG/RENEW COMMAND

=WE CAN FILTER FOR DNS TRAFFIC, WE CAN USE NSLOOKUP IN POWERSHELL TO FIND IP ADDRESSES FOR DOMAIN NAMES LIKE WWW.GOOGLE.COM & WWW.AMAZON.COM :

![image](https://github.com/user-attachments/assets/3f2f975f-7971-42d1-89d9-cc674f379473)

=FINALLY WE CAN OBSERVE REMOTE DESKTOP TRAFFIC BY TYPING IN "TCP.PORT==3389" IN THE SEARCH BAR. YOU WILL NOTICE THERE IS TRAFFIC HAPPENING WITHOUT US DOIN ANYTHING. THIS IS BECAUSE I USED RPD TO CONNECT TO THIS MACHINE
FROM MY OWN COMPUTER AND RDP (REMOTE DESKTOP) SHOWS US A CONSTANT LIVE STREAM OF WHATS HAPPENING :

![image](https://github.com/user-attachments/assets/e8c0761a-f409-42bb-910b-2411ff76a79e)























  


  


  




  


  


