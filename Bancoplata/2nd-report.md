## 2nd Report
After submission of 1st report and I started viewing all public JS files wihtout any tool

## How I found bug
* First I find all JS files using katana and manully viewing network tab on all pages and I created a link of all JS in single file
* Then i downloaded all files at once using wget
* I used command **mkdir js-files && xargs -n 1 wget -P js-files/ < links.txt**
* then I used grep to find hidden secrets and I found sensitive Heroku API
* But the JS file is deleted from server before my report but I still have this file as a POC and they changed API but I have proof

You can see report here :

![Title](/Bancoplata/assets/1.png)
![Report](/Bancoplata/assets/2.png)
![Report-2](/Bancoplata/assets/3.png)
![Report-3](/Bancoplata/assets/4.png)

While i didn't perform all tests together I found some reports during my exams and some after exams but now I am fully in pentesting but the delays make me unable to prove everything properly

As this report was authentic at some time and API is leaked but now they deleted the file and changed API and this report was marked as Informative

![Result](/Bancoplata/assets/5.png)
