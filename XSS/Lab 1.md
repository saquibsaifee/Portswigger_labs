
Lab: Reflected XSS into HTML context with nothing encoded

Vulnerable feature -  This lab contains a simple reflected cross-site scripting vulnerability in the search functionality. 

Goal -  To solve the lab, perform a cross-site scripting attack that calls the alert function. 

Steps: 

1. Access the lab

2. I tried putting xss and it came up in the response![[Pasted image 20230116203509.png]]

3. Let's put the payload of `<script>alert(1)</script>`![[Pasted image 20230116203634.png]]

4. Solved