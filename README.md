#  Gmail_OAuth2.0_testing  
Gmail API using .NET C# with Source Code (Reading mails and Attachments)

this is not my coding but other was doing,

### orignal source code & author,  
https://www.youtube.com/watch?v=0fTSKtPBLUc  
https://drive.google.com/file/d/1PgipOrZBqEbgXCK8VGguR3XSwsk9Ww9T/view  

### ref  
https://developers.google.com/identity/protocols/oauth2  

### my source code mod with prompt   
[GmailAPI_NET_Csharp_Everyday_Be_Coding_Full_Project_prompt_SourceCode.zip](GmailAPI_NET_Csharp_Everyday_Be_Coding_Full_Project_prompt_SourceCode.zip)  

the only thing landed me two hours of testing because no new email in the Gmail inbox, and the original code had no any prompt, so .... adding prompt to the code and then user may see more easy whether gmail fetching via OAuth succeed.  

### Visual studio 2019  
uses Nuget to install Google.Apis.Gmail.v1  
change to my .NET framwork 4.5  

### modified Program.cs

```
                // prompt for user. xiaolaba 2022-MAR-08
                Console.WriteLine("done, you may see return EmailList for unread.");
                Console.WriteLine("if nothing, send email to yourself and then try again.\r\n");
                Console.WriteLine("Gamil read via OAuth2.0");
                Console.WriteLine("ref: https://developers.google.com/identity/protocols/oauth2\r\n");

                Console.WriteLine("orignal source code,");
                Console.WriteLine("https://www.youtube.com/watch?v=0fTSKtPBLUc");
                Console.WriteLine("https://drive.google.com/file/d/1PgipOrZBqEbgXCK8VGguR3XSwsk9Ww9T/view\r\n");

                return EmailList;

```


### modify App.config, change your email address    
```
  <appSettings>
    <add key="HostAddress" value="you_gmail_account@gmail.com" />

```


### create 3 folders
```
C:\GmailAPI\ClientCredentials
C:\GmailAPI\CredentialsInfo
C:\GmailAPI\GmailAttachment
```

### download client_xxxxxxxxxxxx_secret.json, 
save & rename to C:\GmailAPI\ClientCredentials\client_secret.json  


### 成功的畫面  
![succeed.JPG](succeed.JPG)  

### 機器發出的EMAIL, 讀取時有 BUG, 沒時間研究  
![bug.JPG](bug.JPG)  

### 動機, 這個從2011年開始用FAX.TIF, 一直用低安全性等入, CDO 寫的機器, 終於 GOOGLE 說2022年5月30號就斷炊, 所以唯有花時間.  
![initiation.JPG](initiation.JPG)  


## SendMail and utf8
the win10 and batch file, [code page used is 936](https://en.wikipedia.org/wiki/Code_page_936_(Microsoft_Windows)) a default for CHT version, batch file is stored in utf8 (65001 code page), you may hold CTRL+click the link to see wiki of code page 936.
in order to encode properly and dispaly for the command box, uses "chcp 65001", will show properly displayed utf8 string and filename & file content encoded/decoded.
testing files used,
```
sendmail_testing.bat, email address must change to your gmail account before testing
1.txt
1複製.txt
```
![utf8_batch_file.JPG](utf8_batch_file.JPG)    



## further understanding the Gmail.cs & apis and the C# limitation
https://gist.github.com/xiaolaba/d1948372dec2ef235c25bf2b710d132f


