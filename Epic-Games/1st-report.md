## 1st Report
This is my first report to Epic Games 
* I was navigating website and I found a subdomain **api.domain.com**
* Then I checked but access of this domain is denied
* So as always when I got access denied to any domain the only thing I do is directory fuzzing
* Using katana and ffuf I did fuzzing and I found a path where I can access without authentication
* And this path leaks critical data which include APIs, IDs, Sentry DSN and so much more
* I created POC of exploit using curl and proved we can inject and view our data here

Here is my report

![Title](/Epic-Games/assets/1-1.png)
![Report-1](/Epic-Games/assets/1-2.png)
![Report-2](/Epic-Games/assets/1-3.png)
![Report-3](/Epic-Games/assets/1-4.png)
![Report-4](/Epic-Games/assets/1-5.png)

But I am unlucky here this report got duplicated which was a shock for me that time but I motivated by self because duplicates teach us the right path

![Result](/Epic-Games/assets/1-6.png)
