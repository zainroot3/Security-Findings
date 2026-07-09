## A little something to get you started
<img width="1133" height="107" alt="Screenshot_20260709_213604" src="https://github.com/user-attachments/assets/864d85a6-4e4e-40c9-94c4-8b1fbe0fd27d" />

## How to find flag
This CTF displays simple page you can see

<img width="1438" height="755" alt="Screenshot_20260709_213757" src="https://github.com/user-attachments/assets/a59f06cd-5d80-4b17-b1a1-38b739be38b5" />

So to solve this page we can check what source code of this page and we will see this page

<img width="1440" height="900" alt="Screenshot_20260709_213934" src="https://github.com/user-attachments/assets/c191d78b-132b-414f-b4b8-cb80d667fdb7" />

This page is looking normal what when we by looking toward it carefully We can see that in the head section the page is calling background.png in <style> header

<img width="421" height="84" alt="Screenshot_20260709_214046" src="https://github.com/user-attachments/assets/5c8f1d7c-8c2a-4a24-9954-439cd8d789da" />

To further check about this navigate to the network tab and refresh the tab and you will see a request to get this image

<img width="543" height="386" alt="Screenshot_20260709_214242" src="https://github.com/user-attachments/assets/fe69f2b5-a99c-4463-92a3-5858bba2a262" />

To verify this request you can copy from network tab by right clicking on mouse and then press copy as curl or simply copy the url and use command

**curl https://4af587789c5e848f4b35004dcf477310.ctf.hacker101.com/background.png**

And you can see this returns the flag 

<img width="769" height="71" alt="Screenshot_20260709_214433" src="https://github.com/user-attachments/assets/62f08e8a-16dd-4895-b34e-d1e7869e5321" />

## Lession
Static page doesn't mean that the page is fully secure you can check source aur requests of this page and then try to manipulate requests that can be a great vector of attack
