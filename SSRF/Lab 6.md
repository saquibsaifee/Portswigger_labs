https://portswigger.net/web-security/ssrf/lab-ssrf-with-whitelist-filter

Lab: SSRF with whitelist-based input filter

Vulnerable feature -  This lab has a stock check feature which fetches data from an internal system. 

Goal -  To solve the lab, change the stock check URL to access the admin interface at http://localhost/admin and delete the user carlos. 

 The developer has deployed an anti-SSRF defense you will need to bypass. 

Steps: 

1.  Access the lab
2. Launch the BurpSuite
3. Navigate to the stock check feature and capture the request
4. We see the stockApi and after URL decoding it using `ctrl+shift+u` we changed it to localhost and we see it is blocked