# Cyber Threat Intelligence integrated with Splunk

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

- Open CTI
- Splunk server
- Linux
- Windows
- Docker Compose


# Steps

Fig1: FoxyProxy extension is install in Firefox
![Capture](https://github.com/user-attachments/assets/8bfb5514-b304-4992-81c1-62d762d843a5)

Fig2: Proxyfox is configure to work with Burp Suite.
![Capture](https://github.com/user-attachments/assets/87bda66b-f559-4d2c-8108-e45032a76e5e)

Fig3: Let's test the security on the following website.
![Capture](https://github.com/user-attachments/assets/73aec982-24ea-488d-a642-fa58a4fd6a88)

Fig4: In the site mapping under the Target menu, we found information revealing a GET request on a hidden link we discovered.
![Capture1](https://github.com/user-attachments/assets/7faf92f6-363c-4a73-b0d6-a6f50a28363d)

Fig5: It's confirmed that we could access and read the information by visiting the previously discovered link.
![Capture](https://github.com/user-attachments/assets/14771851-62c7-470d-b8e4-8cde66dd906e)

Fig6: Testing for stored XSS on the website's ticket submission form.
![Capture](https://github.com/user-attachments/assets/8e7c7855-f5b8-4390-ab36-062c4760fc88)

Fig7: Request intercepted by Burp Suite Repeater.
![Capture1](https://github.com/user-attachments/assets/48de92ec-6cc5-4c32-a302-55038da948a7)

Fig8: The request was modified with JavaScript code and forwarded back to the web server.
![Capture1](https://github.com/user-attachments/assets/dbec42c9-ac4e-4869-8962-be0a8eb5c5d1)

Fig9: We successfully injected the malicious JavaScript code into the web application, confirming that the website is vulnerable to XSS (Cross-Site Scripting).
![Capture](https://github.com/user-attachments/assets/1106664a-0fc4-469c-8bb5-de82d4757ff6)
