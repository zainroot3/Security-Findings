## 7th Report
This is my favourite report ever becuase this is not a low hanging fruit and logical mind is required for this
I find this vulnerability after complating my JWT Tokens room in tryhackme because both have authentication phase here
* I was intercepting login requests and I found bank using /api/otp/send endpoint to send sms
* Then to verify I also intercepted that bank using same endpoint with different path /api/otp/verify
* So I found send and verify API
* Then in JSON I found it contain phone number and id in /otp/send and addition otp in /otp/verify
* First I tried changing id in /otp/verify using burp suite but phone and id should be same
* And then I noticed bank is verifying phone by id that was used in /otp/send with phone
* Then I changed id in /otp/send and used this id in /otp/verify with same phone number
* This game me additional 5 attempts ant I tried this with more then 1000+ attempts using turbo intrudor extension
* The system haven't detected the requests coming from same phone number
* Because backend is verifyin id not phone number which is in user control
* In this way I bypassed rate limiting and not tried for otp bypass
* Because I don't have valid phone number for mexico to try that's why I stopped
* The one issue I found too that the browser blocks when we send otp for 3 times but for burp suit we can do it many times
* Even WAF haven't detected
* After almost 1500 requests from the same ip address WAF restricted by ip to only 5 requests
* But in this case we bypassed logic of backene

Here is report

![Title](/Bancoplata/assets/7-1.png)
![Report](/Bancoplata/assets/7-2.png)
![Report-2](/Bancoplata/assets/7-3.png)

But my badluck I also got this duplicated but the good news is that triager appreciated me and this is valid bug and the original report got **9.3 severity** and only 1 person found this before me

![Result](/Bancoplata/assets/7-4.png)

This is my favourite report although it got duplicated but the point is this I am on the right path
