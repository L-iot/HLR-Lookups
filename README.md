# HLR-Lookups
This script is used to automate the HLR-lookup process by using the api from hlr-lookups and it extracts important data from it like the IMSI of the subscriber, which country  he/she is roaming in ,provided by the current MSC GT along with the HLR GT, these information could be useful to conduct further attacks... using Sigploit.

It must be noted that those public services like HLR-Lookups are using a variant of SS7 messages that is most probably SendRoutingInformationForSM(SRISM) which is used to locate the target location before sending SMS, some operators implement an SMS Firewall/proxy that scrambles the IMSI and/or HLR and returns back a fake MSC. To overcome this kind of protection its always recommended to perform Transaction Capabilities Application Part (TCAP) scanning on the range of the GT as the implementation of such scrambling is very weak and predicatedble. Therefor its recommended to run the script twice for each msisdns to make sure that the returned information is the same and is not changing per request

This script currently works for

-Qtel

-Zain KW

-Etisalat UAE

-DU UAE

-jawal palestine 

-India (Airtel, Reliance, Vodafone)

-Russia (MTS)


This lookup is by no means  comprehensive  and shouldnt be the only way to gather information

The script also could detect if home routing (SMS FW) is being implemented

# How does it work
1- First you need to create an account on HLR-Lookups which will give you free credit at the beginning along with the API username and passwords that will be used in the script

2- run the script as below

Usage: ./hlr-lookup.py MSISDN
  
Example: ./hlr-lookup.py +20123456789

Please note: You may need to change the route (route="") if the results are uncertain.
