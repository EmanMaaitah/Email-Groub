# OBJECTIVE 
More than one activity is tried using Use Gmail resources Based on many activities
## MANUALLY
1) Opening any email will be marked Read/Unread.

# TECHNICAL REQUIREMENTS

## Use Gmail Activities
1) [Use Gmail](https://docs.uipath.com/activities/other/latest/productivity%22/gmail-application-card)
2) [For Each Email](https://docs.uipath.com/activities/other/latest/productivity/for-each-email-x)
3) [Save Email Attachments](https://docs.uipath.com/activities/other/latest/productivity/save-mail-attachments-x)
4) [Save Email](https://docs.uipath.com/activities/other/latest/productivity/save-mail-x)
5) [Forward Email](https://docs.uipath.com/activities/other/latest/productivity/forward-mail-x)
6) [Delete Email](https://docs.uipath.com/activities/other/latest/productivity/delete-mail-x)
7) [Move Email](https://docs.uipath.com/activities/other/latest/productivity/move-mail-x)

###  If Activity
   [If Activity](https://docs.uipath.com/studio/standalone/2023.10/user-guide/the-if-activity)
   
## UI Automation Activities
1) [Message Box](https://docs.uipath.com/activities/other/latest/workflow/message-box)


# PROCEDURES
#### First activity
1) Use Gmail activity in the Account field Enter your email address and connect it to your account


   <img src="https://github.com/user-attachments/assets/437346d6-8c62-46de-b7b8-f8d1da44ea57" width="400">
   

2) For Each Email activity > Inside in Email from field Select folder inbox > select limit and make checks


   <img src="https://github.com/user-attachments/assets/4a403fb4-d9b0-4d08-91b9-bf263d15120b" width="400">


3) Print the mail subject  to verify it using a variable CurrentMail.Subject through Message Box
4) Use If Activity inside the condition box write CurrentMail.Body.Contains("read ")
5) Inside Then use Mark Email As Read/Unread activity and select CurrentMail variable.

   <img src="https://github.com/user-attachments/assets/bba83683-1cb0-43b0-9444-e94326c069de" width="400">
 

6) You can check about the name of sender and the content beside The date the message was sent. using the following commands

   <img src="https://github.com/user-attachments/assets/e3941f00-0324-4fd9-ac63-5575edc2ef89" width="400">
   

#### Second activity
1) Use If Activity inside the condition box write CurrentMail.Body.Contains("save") OR CurrentMail.Body.Contains("Save")
2) Use Save Email 


   <img src="https://github.com/user-attachments/assets/956bb701-5560-4dff-9cf6-12da73739d14" width="400">

#### Third activity
* To download attachments:
1) Use If Activity inside the condition box write CurrentMail.Body.Contains("download")
2) Use Save Email Attachments> Enter in filter by file name "*.pdf"

   
   <img src="https://github.com/user-attachments/assets/1493cdd4-95a3-43fc-964a-5e0f28a9650b" width="400">
   
#### 4th activity
* To Forward Email:
1) Use If Activity inside the condition box write CurrentMail.Body.Contains(" forward")
2) Use Forward Email > inside the add "To" resipients add an email

   <img src="https://github.com/user-attachments/assets/a8b7118c-3c21-4b8e-8519-27675e98bf29" width="400">
   
#### 5th activity
* To Delete Email:
1) Use If Activity inside the condition box write CurrentMail.Body.Contains("delete ")> Delete Email


   <img src="https://github.com/user-attachments/assets/2bc8c866-61e1-4bf1-b691-2db2946f030c" width="400">  

#### 6th activity
 * To Move Email: 
 1) Also inside the for each email use Move Email > select the destination inside move to (all emails will be transfer to Draft)

    <img src="https://github.com/user-attachments/assets/da57fcfb-ff3d-4722-980b-7b3b90a6b929" width="400"> 
  

# CONCLUSION
1) CurrentMail Variable stays within scope For Each Email It can not be used outside the scope.
2) There are many commands used beside CurrentMail Variable :(Body, DateAsDateTime,From) and you can print them once transfered to string (.toString)
