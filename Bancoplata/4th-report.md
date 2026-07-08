## 4th Report
I submitted this report during final exams of my college
* When enumerating subdomains i found a subdomain **empresa.domain.com**
* But this domain redirect me to the authentication page but that doesn't mean this domain contain nothing
* I fuzzed directories and I found a path **empresa.domain.com/envs** but this also redirect toward the authentication page
* Then i also fuzzed for files and i found location **https://empresa.domain.com/envs/env.json** When i opened this JSON this opened wihtout any authentication and has lot of data from which this file also exposes a paybable Google API key

 This is my Report

 ![Title](/Bancoplata/assets/4-1.png)
 ![Report](/Bancoplata/assets/4-2.png)
 ![Report-2](/Bancoplata/assets/4-3.png)

 But my badluck I got thir report duplicate by just 3 hours 

 ![Result](/Bancoplata/assets/4-4.png)

 But this motivated me more then I am moving from low hanging to logical thinking
