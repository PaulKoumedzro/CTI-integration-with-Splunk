# Investigate SSH brute-force with Splunk

# Objective

The goal of this lab is to simulate a real-world SSH brute-force investigation using Splunk. I will ingest SSH authentication logs, users locations, craft targeted SPL searches to detect repeated failed login attempts, and correlate those events to pinpoint the attack vectors.


# Skills Learned
- Setting up and Configuring Splunk
- Learn element that make up splunk such Index, Universal forwarder and Search bar.
- Write splunk query (SPL)
- Create & save dashboard
- Filter search
- Create an alert.
- create & schedule a report
- Follow Splunk best practice.
- Correlate SSH faileures and network traffic data to map attack patch.


# Tools Used

- Splunk


# Steps

Fig1: Logs containing the keyword 'failed' were retrieved using a date and time filter in conjunction with the index 'mydfir-lab1
<img width="1915" height="982" alt="1" src="https://github.com/user-attachments/assets/91bd6c06-607a-46e3-91f0-12ffef7c5b5b" />

Fig2: As part of Splunk search best practices, we'll open an event to review all available fields and determine which ones we can leverage in our query.
![2](https://github.com/user-attachments/assets/5015e641-442b-48f9-84b2-c4dbf0910795)

Fig3: The default fields will now be used to perform a search for the top users.
![3](https://github.com/user-attachments/assets/2752875a-e64c-4561-8852-2bb1765ad65d)


Fig4: We now see that our top failed user is root
![2](https://github.com/user-attachments/assets/45c26db2-ef0c-4656-85c7-43bd0f085970)

Fig5: using the "src_ip" field appended to the previous command we now see the top source IP 
<img width="1911" height="971" alt="image" src="https://github.com/user-attachments/assets/9cbbbcab-d04b-4f96-94fd-eaba0ec47b2c" />

Fig6: Failed Authentication by User.
<img width="1918" height="930" alt="image" src="https://github.com/user-attachments/assets/674b526f-0f97-4e37-9799-f01ef0fe2be4" />

Fig7: We'll now search for successful authentication events to determine if any users were able to access SSH successfully
<img width="1919" height="985" alt="image" src="https://github.com/user-attachments/assets/383da165-3fef-46f7-8dee-c998f368d5e3" />

Fig8: Heatmap of network activity is created to visualize what countries the source IPs orginated from.
<img width="1918" height="993" alt="image" src="https://github.com/user-attachments/assets/58e80111-a894-49ea-8c72-679d5388777a" />

Fig9: Creation of new dashboard titled "SSH Activity" to save  search results.
![1](https://github.com/user-attachments/assets/28954959-b40c-4922-8b70-8b2b96ee0f3e)

Fig10: Searches are saved into dashboard for later visualization and analysis.
<img width="1917" height="990" alt="image" src="https://github.com/user-attachments/assets/3c6010cf-a084-45f4-bf02-ee284badede7" />
