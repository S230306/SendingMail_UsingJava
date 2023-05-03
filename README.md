
Project Title:
Java Email Application

1. Project Description:
Using JavaMail API to send emails using SMTP from Java applications:

without authentication,
with TLS Authentication,
with SSL Authentication and Email attachment and image.
2. Tech Stack:
Java 9
JavaMail API
Gmail SMTP server
3. Installing:
i. Clone the git repo

https://github.com/AAdewunmi/Java-Email-Application.git
ii. Open project folder

iii. Explore

😎

4. How To Use:
To send emails:

without authentication -> Run in IDE -> src/main/java/com/application/SimpleEmail.java,
with TLS Authentication -> Run in IDE -> src/main/java/com/application/TLSEmail.java,
with SSL Authentication and Email attachment and image Run in IDE -> src/main/java/com/application/SSLEmail.java.
5. JavaMail API Troubleshooting Tips:
java.net.UnknownHostException comes when your system is not able to resolve the IP address for the SMTP server, it might be wrong or not accessible from your network. For example, GMail SMTP server is smtp.gmail.com and if I use smtp.google.com, I will get this exception. If the hostname is correct, try to ping the server through command line to make sure it’s accessible from your system.
      
