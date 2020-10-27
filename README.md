Monitor Azure VM Availability
=============================

            



 
The idea behind writing this script is to have an automated solution to monitor availability of any Azure VMs. The script fetches the current server status, saves it in an Azure Table. Each script execution is one poll. So the second time the script runs, it
 fetches the current server status of VMs and then compares it to the previous value. if there is any changes to the server status during polling, such server details will be written to a hash table. Finally the details of the servers can be sent to an email.




Since we are monitoring the VM status from 'RUNNING' to 'VM STOPPED', this will eliminate the scenarios, where VMs are stopped manually or as per a scheduled shutdown automation sctipt. In these cases the VM status changes from 'RUNNING' to 'VM DEALLOCATED'.


Feel free to customize the script to add logic if you want to monitor the status of De-allocated VMs as well.


This script uses SendGrid as an email server. Feel free to add your SMTP address if you have one.


This script is use full when you do not yet have a fully automated monitoring like Nagios/OMS. Maybe you just have couple of servers that you want to monitor and do not want to spend more money on a custom monitoring. Just create a runbook using this script
 as a baseline and schedule it in the Azure Automation Account.


 


 


        
    
TechNet gallery is retiring! This script was migrated from TechNet script center to GitHub by Microsoft Azure Automation product group. All the Script Center fields like Rating, RatingCount and DownloadCount have been carried over to Github as-is for the migrated scripts only. Note : The Script Center fields will not be applicable for the new repositories created in Github & hence those fields will not show up for new Github repositories.
