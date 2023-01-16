Lab #2 - Basic SSRF against another back-end system

Vulnerable feature -  This lab has a stock check feature which fetches data from an internal system. 

Goal - To solve the lab, use the stock check functionality to scan the internal 192.168.0.X range for an admin interface on port 8080, then use it to delete the user carlos. 

Steps: 

1. Access the lab
2. Launch the BurpSuite
3. Navigate to the stock check feature and capture the request
4. We see the stockApi and after URL decoding it usign `ctrl+shift+u` it looks like this![[Pasted image 20230115185405.png]]
5. Let's launch a dictionary attack on last octet of the ip `192.168.0.x` using intruder `ctrl+i`![[Pasted image 20230115190251.png]]
6. Payload will be numbers from 1 - 255 ![[Pasted image 20230115190320.png]]
7. Our attack is done we found `192.168.0.247\admin` gives `200` ![[Pasted image 20230115190750.png]]
8. Let's go there and try to find the endpoint the delete the user carlos![[Pasted image 20230115190959.png]]
9. Let's try to use it and we get 302 which is good.![[Pasted image 20230115190946.png]]
10. ![[Pasted image 20230115191103.png]]

