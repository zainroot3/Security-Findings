## 2nd Report
This was my worst report 
* I was discovering endpoints on domain.com
* And I found a subdomain **sub.domain.com**
* When I visited this the access to page is denied
* But after fuzzing directory I found a path **sub.domain.com/path/path1/path2/admin** which was publicly accessible and contain API key in client side HTML
* I suddenly checked and it have admind previliges like listINdex
* I reported this

Here is the report

![Title](/Epic-Games/assets/2-1.png)
![Report](/Epic-Games/assets/2-2.png)
![Report-2](/Epic-Games/assets/2-3.png)

But the triager was not satisfied and after a huge conservation with triager he marked the submission as not applicable

![Result](/Epic-Games/assets/2-4.png)

This was also a good lession for me to never report until you can't fully prove the impact
