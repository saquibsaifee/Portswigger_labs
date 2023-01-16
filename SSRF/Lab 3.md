Lab #1 - SSRF with blacklist-based input filter

Vulnerable feature -  This lab has a stock check feature which fetches data from an internal system. 

Goal -  To solve the lab, change the stock check URL to access the admin interface at http://localhost/admin and delete the user carlos.

The developer has deployed two weak anti-SSRF defenses that you will need to bypass. 

Steps:

1. Access the lab
2. Launch the BurpSuite
3. Navigate to the stock check feature and capture the request
4. We see the stockApi and after URL decoding it using `ctrl+shift+u` we changed it to localhost and we see it is blocked![[Pasted image 20230115191637.png]]
2. We tried 127.0.0.1 and it is also blocked![[Pasted image 20230115192644.png]]
3. what about `127.1`, looks like we have bypassed the block![[Pasted image 20230115192708.png]]
4. Now we check `127.1/admin` and it is blocked. To bypass it we double URL encoded `a` of `admin`![[Pasted image 20230115192412.png]]
5. We found the URL endpoint to delete the user `carlos` and we got the 302.![[Pasted image 20230115192442.png]]
6. After changing the stockApi we solved again.![[Pasted image 20230115192508.png]]