# APIC-Gateway-Extension-override-parse-setting

This is an API Connect gateway-extension sample for overriding the default payload max size (default is 4 MBs).
This gateway-extension increases the size to 10 MBs.

NOTE: This is a very high size limit and is not suggested. This is only for demo purposes.

The following is the original default 4 MB sizing for the max document size:  
<img width="835" height="521" alt="image" src="https://github.com/user-attachments/assets/b8d93462-e682-4f84-b6ab-7d387310dd81" />


After uploading the gateway-extension to the gateway from the topology, and restarting the gateway pod, the size will be updated:  
<img width="849" height="523" alt="image" src="https://github.com/user-attachments/assets/18e7bb08-da16-4447-a9cd-2b21a55de60e" />



