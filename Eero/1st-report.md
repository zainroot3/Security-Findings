## 1st Report
I was learning oAuth in tryhackme and portswigger in parallel here I was studying about redirection and I become curios to test this on real world so I choosed a target to test how actually real world oAuth looks likes
* I choosed a domain domain.com which is unresponsive but this doesn't mean we can stop here then I decided to find subdomains
``` bash
subfinder -d domain.com | puredns resolve | httpx -status-code | grep 200
```
* I used this command to find all available valid subdomains and I found a interesting subdomain preprod.insight.domain.com
* When i visited this domain I found this use account which are already created we can't create account but there I found a button login as SSO then login as support that would be a great target even scope se small
* I started intercepting requests and I found a request with redirect parameter which I found interesting for some tests

![image](/Eero/assets/1.png)

* The interesting thing is it goes to sso.domain.com and refer as preprod.insight.domain.com that's a whole chain then I started changing redirect parameters
* I changed domain tried path traversal and all common techqnques but only two technques got worked which I reported from which I will discuss one here
* First I trying added this extra part in redirect url like

```
https://domain.com &@foo.evil-user.net#@bar.evil-user.net
```
* Then this request returned 500 internal server crash that's not a vulnerability but it's cleared sign that WAF bypassed and our request goes to server and no error occurs
* Then I started changing requests and at last I found this bypass techniques that workd by encoding them in url and shows redirect and I found the url is stored in cookie when I encoded the cookie

![image](/Eero/assets/2.png)

Then I don't have valid credentials to test this further so I reported this Here you can see my report

![title](/Eero/assets/Screenshot_20260718_125650.png)
![photo](/Eero/assets/3.png)
![image](/Eero/assets/4.png)
![image](/Eero/assets/5.png)

But unfortunalty I got this report duplicate

![Result](/Eero/assets/6.png)

BUt that doesn't meam game is over it's just tha start of real journey
