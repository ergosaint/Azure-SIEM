
# Azure SOC Lab

## Objective

Creating my very own Security Operations Center and Setting up a Security Information and Event Management (SIEM) system through Microsoft Azure
### Skills Learned

- How to navigate Microsoft Azure directory
- Advanced understanding of SIEM concepts and practical application.
- Proficiency in analyzing and interpreting network logs.
- Connecting SIEM to Virtual Machine for data collection

### Tools Used

- Microsoft Azure to host Virtual Machine and run SIEM
- Microsoft Sentinal Security Information and Event Management (SIEM) system for log ingestion and analysis.

## Steps
1. Sign up for Microsoft Azure
2. Follow promps to create Virtual Machine
   - Create resource group "Solanin" (container for everything created)
   - Image: Windows 11 pro Version 23H2 - x64 Gen3
   - Leave RDP ports open for our detection
   
![Screenshot 2024-10-31 011344](https://github.com/user-attachments/assets/cc3022a2-9ccf-4d73-a7a2-579b5dbf1bbf) *Ref 1: Virtual Machine i've named FatherVM*

3. Add Microsoft Sentinel (a cloud-native security information and event management (SIEM) platform) to a log analytics workspace
   - Create log analytics workplace and add to resource group "Solanin-LogAnalytics"

4. Connect VM to Microsoft Sentinal Workspace so I can start generating event logs recieved
   - Add sentinal to Log Analytics workspace
   - Data connector: Windows Security Events
   - Create data collection rule "WindowsEventstoSentinal"
    
5. Set up dashboard
   
![Screenshot 2024-10-31 022450](https://github.com/user-attachments/assets/a7e1f864-456f-4952-8f33-fd5a540e8037) *Ref 2: Incident Dashboard*


6. Create detection rule (RDP succesfull logins into VM)
   
![Screenshot 2024-10-31 022009](https://github.com/user-attachments/assets/9c9ef61d-745c-4fc8-935b-63c6f73216fe) *Ref 3: Rule Setup*

7. Succesfully created a Honeypot for  RDP connections !!!!!
   
