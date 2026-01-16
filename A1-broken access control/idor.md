# Insecure Direct Object Reference (IDOR)
**OWASP Top 10 – A01: Broken Access Control**

---

## Vulnerability Overview
Insecure Direct Object Reference (IDOR) occurs when an application exposes
internal object references (such as file names or IDs) and allows attackers
to manipulate them to access unauthorized resources without proper
authorization checks.

---

## Lab Environment
- Platform: PortSwigger Web Security Academy
- Lab Type: Insecure Direct Object References
- Vulnerability Category: Broken Access Control
- Tools Used: Burp Suite

---

## Description
The application provides a chatbot feature that allows users to download
a transcript of their chat conversation as a text file.

The filename used to retrieve the chat transcript is directly referenced
in the request and is not properly validated on the server side.
By modifying the filename parameter, it is possible to access other
files belonging to different users.

---

## Steps to Reproduce

1. Log in to the application as a normal user
2. Navigate to the **Chat Bot** page
3. Interact with the chatbot to generate a chat conversation
4. Download the chat transcript, which is saved as a file (e.g., `2.txt`)
5. Intercept the download request using **Burp Suite**
6. Modify the filename parameter from:
