**Author:** Safal

**Date:** 2025-10-22  

**Tools:** Splunk (analysis & export), whois lookup  


Challenge URL: https://blueteamlabs.online/home/challenge/bruteforce-16629bf9a2 

Splunk queries
To see the lowest and highest port 
index=btlo-index sourcetype=csv  
| rex field=EXTRA_FIELD_6 "Source Port:\s+(?<src_port>\d+)" 
| stats min(src_port) as Lowest_Port, max(src_port) as Highest_Port 

To see all the ports with event 
index=btlo-index sourcetype=csv  
| rex field=EXTRA_FIELD_6 "Source Port:\s+(?<src_port>\d+)" 
| table _time src_port host source 

Country Extraction and visualization 
index=btlo-index sourcetype=csv  
| rex field=EXTRA_FIELD_6 "Source Network 
Address:\s+(?<src_ip>\d{1,3}(?:\.\d{1,3}){3})" 
| iplocation src_ip 
| stats count by Country 
| sort -count 

With Username and success failure 
index=btlo-index sourcetype=csv  
| eval Status=if(match(EXTRA_FIELD_6, "An account failed to log on"), 
"Failure", "Success") 
| rex field=EXTRA_FIELD_6 "Account Name:\s+(?<username>\S+)" 
| stats count by Status, username 
| sort - count
