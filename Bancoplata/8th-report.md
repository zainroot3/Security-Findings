## 8th Report
This is low hanging fruit and my 8th report on the same platform
* I opened a subdomain **events.domain.com**
* This domain displays the error message of framer
* That verifies bank use framer for this domain and now this domain expired
* I used this pipeline to verify

```bash
subfinder -d domain.com | puredns resolve | httpx -status-code | grep 404 | cut -d " " -f 1 | nuclei -t nuclei-templates -tags Takeover
```
* Thid command displayed a domain **event.domain.com**
* So to verify manually I first used command 
```bash
dig event.domain.com
```
* This command verifies CNAME and proves this is valid takeover
* Then to verify further I used below command and I found domain is not in any ownsership
```bash
curl -I event.domain.com
```
* Because when I visit subdomain the page also shows 404
* I created framer account and I found takeover is possible
* Then I reported this vulnerability

Here is my report

![Title](/Bancoplata/assets/8-1.png)
![Report](/Bancoplata/assets/8-2.png)

But as it is low hanging fruit I already know that this report will got duplicate but as a responsible hackers its our responsibility to remind company that's your issue still not fixed

![Report](/Bancoplata/assets/Untitled%20design.png)
