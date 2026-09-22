# APIC-Gateway-Extension-override-parse-setting

This is an API Connect gateway-extension sample for overriding the default payload max size (default is 4 MBs).
This gateway-extension increases the size to 10 MBs.
The parse settings are located in the apiconnect domain > Parse Settings > apic-default-parsesettings.

NOTE: This is a very high size limit and is not suggested. This is only for demo purposes.

The following is the original default 4 MB sizing for the max document size:  
<img width="835" height="521" alt="image" src="https://github.com/user-attachments/assets/b8d93462-e682-4f84-b6ab-7d387310dd81" />


After uploading the gateway-extension to the gateway from the topology, and restarting the gateway pod, the size will be updated:  
<img width="849" height="523" alt="image" src="https://github.com/user-attachments/assets/18e7bb08-da16-4447-a9cd-2b21a55de60e" />

The [gw-extension.zip](https://github.com/ibmArtifacts/APIC-Gateway-Extension-override-parse-setting/blob/main/gw-extention.zip) is ready to be uploaded to the gateway in the topology to be used.
You may unzip and update the value per your needs.

To deploy the zip, navigate to the gateway in the topology section of the Cloud Manager, click on the ellipse (dot-dot-dot) of the gateway to choose Configure Gateway Extension.
<img width="1198" height="799" alt="image" src="https://github.com/user-attachments/assets/b8a23e42-6555-4cd1-bb4b-9ce14d59e92f" />

After restarting the gateway, the changes will be reflected once the gateway comes back online.


## Appendix
### gw-extension files
#### override-parse-defaults.json
```  
{
  "parse-settings":{
     "_global":{
        "override":[
           "document-size 1048576"
        ]
     }
  }
}
```


#### manifest.json
```  
{
   "extension":{
      "files":[
         {
            "filename":"override-parse-defaults.json",
            "deploy":"immediate",
            "type":"gwd_extension"
         }
      ]
   } 
}
```  




