# Investigate SSH brute force with Splunk

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


Fig9: We successfully injected the malicious JavaScript code into the web application, confirming that the website is vulnerable to XSS (Cross-Site Scripting).
![Capture](https://github.com/user-attachments/assets/1106664a-0fc4-469c-8bb5-de82d4757ff6)
