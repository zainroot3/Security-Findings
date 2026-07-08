## 5th Report
This is my 5th report on the same target of XSS and file upload bypass
* I found a interesting subdomain **career.domain.com**
* This domain is interesting becacuse this have a job apply page
* When I check this page the first name page is vulnerable to html and JS injection while other fields are protected
* This form also have pdf resume upload option
* While this is securly managed but some client side logics are not correctly secured
* To upload a php file I tried shell.php.pdf but this fails
* Then I tried adding %PDF-1.1 on the top of file
* And server accepted this
* But when I intercepted the request using burp suite the pdf is converted into base64 in client side
* Then in burp i removed base64 and added **<script>alert("bug-bounty-test");</script>**
* And this payload was successfully send without any verification

This is my Report

![Title](/Bancoplata/assets/5-1.png)
![Report](/Bancoplata/assets/5-2.png)
![Report](/Bancoplata/assets/5-3.png)

But unfortunately this report also marked as duplicate because I choosed bank as my life first target not a VPD or any insecure platform

![Result](/Bancoplata/assets/5-4.png)

But it is also a sign that I am on right side finding complex vulnerabilities
