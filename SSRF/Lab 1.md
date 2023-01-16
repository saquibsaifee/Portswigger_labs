Lab #1 - 

Vulnerable feature - This lab has a stock check feature which fetches data from an internal system.

Goal - To solve the lab, change the stock check URL to access the admin interface at `http://localhost/admin` and delete the user `carlos`.

Steps: 

1. Access the lab 
2. Open the BurpSuite
3. Navigate to the stock check feature and capture the request in burp
4. We see this stockApi, let's decode it using `ctrl+shift+u` ![[Pasted image 20230115184444.png]]
5. Let's see if we can access the localhost from here after sending the request into `Repeater` using `ctrl+R`![[Pasted image 20230115184502.png]]
6. We have access the localhost from here and we have `Admin Panel`
7. Let's go to admin panel see what's there![[Pasted image 20230115184520.png]]
8. We can see the `carlos` user and option to `delete it`, we just need to find the `URL` to delete
9. After searching the `carlos` in the raw data we found the endpoint to delete a user![[Pasted image 20230115184547.png]]
10. This is look promising because of `302` as it is deleted.![[Pasted image 20230115184613.png]]
11. ![[Pasted image 20230115184337.png]]
