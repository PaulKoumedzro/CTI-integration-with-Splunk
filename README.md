# Web Application Testing Lab with Burp Suite

# Objective

The Web application penetration Testing lab is to demonstrate web application security testing using Burp Suite, a powerful suite of tools used to identify and exploit vulnerabilities in web applications. This lab provides a safe, controlled environment to explore and showcase various Burp Suite tools, including intruder, repeater, scanner, and proxy,  and provide step-by-step guidance on using Burp Suite to discover and analyze vulnerabilities.


# Skills Learned
- Setting up and Configuring Burp Suite: configuring the Burp Suite proxy settings to intercept HTTP/HTTPS traffic
- Intercepting and Manipulating HTTP Requests: capturing requests and responses with the Proxy tool.
- Modifying  request parameters,headers, and cookies for manual testing.
- Runing scans to detect common web vulnerabilities like SQL injection, XSS, and CSRF.
- Testing session management to identify insecure session handling and cookie weakness.
- Manual vulnerability Testing with Repeater.Repeating and modifying requests to test for SQLi,XSS and other input-based vulnerabilities.
- Using Intruder to brute-force login and bypass authentication.
- Utilizing the Target tool to map the web application's endpoints and understand its structure.
- Learning about secure coding practices to mitigate identified vulnerabilities.
- Documenting vulnerabilities,their impact, and their potential remediation.
- Exporting reports and organinizing findings for stakeholders.


# Tools Used

- Burp Suite Community Edition for Web application Penetration Vulnerability testing. A very powerful tool for Web application security testing,SQLi, XSS,CSRFintercept request,modify them,craft payloads.


# Steps

Fig1: Install FoxyProxy extension in Firefox
![Capture](https://github.com/user-attachments/assets/8bfb5514-b304-4992-81c1-62d762d843a5)

Fig2: Configure the Proxyfox to work with Burp Suite.
![Capture](https://github.com/user-attachments/assets/87bda66b-f559-4d2c-8108-e45032a76e5e)

Fig3: Let's test the security on the following website.
![Capture](https://github.com/user-attachments/assets/73aec982-24ea-488d-a642-fa58a4fd6a88)

Fig4: Discovered some information in the site maping  under Target menu.we can see a GET request on the hidden link we dicovered.
![Capture1](https://github.com/user-attachments/assets/7faf92f6-363c-4a73-b0d6-a6f50a28363d)

Fig5: we can see that we were able to access and read the information when we visit the link discovered previously.
![Capture](https://github.com/user-attachments/assets/14771851-62c7-470d-b8e4-8cde66dd906e)

Fig6: Testing stored XSS on the webiste ticket submission form
![Capture](https://github.com/user-attachments/assets/8e7c7855-f5b8-4390-ab36-062c4760fc88)

Fig7: Rrequest intercepted by Burp Suite Repeater.
![Capture1](https://github.com/user-attachments/assets/48de92ec-6cc5-4c32-a302-55038da948a7)

Fig8: Request modified with Javascript code and forward back to the web server
![Capture1](https://github.com/user-attachments/assets/dbec42c9-ac4e-4869-8962-be0a8eb5c5d1)

Fig9: we successufully inject the malicious Javascript code into the web app and confirm that the web site is vulnerable to XSS (Cros-site Scripting).
![Capture](https://github.com/user-attachments/assets/1106664a-0fc4-469c-8bb5-de82d4757ff6)





# SQL inJection Lab

The objective in this lab is to identify and exploit a Union SQL Injection vulnerability present in the ID parameter of the /about/ID endpoint of a Web application. By leveraging this vulnerability, with the help of Burp Suite, an attack to retrieve the notes about the CEO stored in the database.



# Tools Used

- Burp Suite Community Edition for Web application Penetration Vulnerability testing. A very powerful tool for Web application security testing,SQLi, XSS,CSRFintercept request,modify them,craft payloads.


# Steps

Fig1: Here is the website we are testing the SQLi on. Let's visit the CEO profile page since it's our target here.
![Capture](https://github.com/user-attachments/assets/a16fb162-bdaa-4118-8008-92f99cfcb08f)


Fig2: Burp Suite Proxy is used to intercept the request and Foward it to the repeater.
![Capture](https://github.com/user-attachments/assets/1b2d02fe-304a-4ac6-8a55-8a7152f6340d)


Fig3: Let's confirm that an SQL vulnerability exists by adding a single apostrophe (') to the /about/2 path in the request view. We can see in the Response view a confirmation that the vulnerability actually exists.
![Capture](https://github.com/user-attachments/assets/7fd27d99-5681-4734-b1b9-b839a2908ba4)


The message tells us a couple of things that will be invaluable when exploiting this vulnerability:

The database table we are selecting from is called people.
The query selects five columns from the table: firstName, lastName, pfpLink, role, and bio.

Fig4: We will try to retreive all info contained in the people table.Using the following command
/about/0 UNION ALL SELECT group_concat(column_name),null,null,null,null FROM information_schema.columns WHERE table_name="people"
We have a complete information about the table in the Request view.
![Capture](https://github.com/user-attachments/assets/831ca78e-f1a3-4146-ab5f-306b2b7e4617)

Fig5: Now that we have successfully identified eight columns in this table: id, firstName, lastName, pfpLink, role, shortRole, bio, and notes, let's craft a query accordingly to exctract the information from the database.
0 UNION ALL SELECT notes,null,null,null,null FROM people WHERE id = 1
![Capture](https://github.com/user-attachments/assets/aa78dc3a-8e39-44bf-b3ef-6040d1564ce0)

The information stored in the database is THM{ZGE3OTUyZGMyMzkwNjJmZjg3Mzk1NjJh}
