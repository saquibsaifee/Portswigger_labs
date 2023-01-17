Lab: SSRF with filter bypass via open redirection vulnerability

Vulnerable feature -  This lab has a stock check feature which fetches data from an internal system.

Goal -  To solve the lab, change the stock check URL to access the admin interface at http://192.168.0.12:8080/admin and delete the user carlos.

The stock checker has been restricted to only access the local application, so you will need to find an open redirect affecting the application first. 

Steps: 

1. This is different is not a URL but a path.![[Pasted image 20230115194539.png]]
2. But we see a new functionality which is `Next Product`. Hovering on it shows the URL which has a interesting parameter `path=`![[Pasted image 20230115200433.png]]
3. Let's capture the request![[Pasted image 20230115200505.png]]
4. Let's try to redirect it to `https://www.google.com`![[Pasted image 20230115200910.png]]![[Pasted image 20230115200900.png]]
5. It worked. Now let's redirect it to the `192.168.0.12:8080/admin` but in the check stock feature![[Pasted image 20230115201200.png]]
6. Let's URL encode it and try again![[Pasted image 20230115201234.png]]
7. It worked. Now let's delete the carlos![[Pasted image 20230115201317.png]]
8. ![[Pasted image 20230115201348.png]]