## A little something to get you started
![Title](/Hackerone-CTFs/assets/Screenshot_20260709_213604.png)

## How to find flag
This CTF displays simple page you can see

![image](/Hackerone-CTFs/assets/Screenshot_20260709_213757.png)

So to solve this page we can check what source code of this page and we will see this page

![source-code](/Hackerone-CTFs/assets/Screenshot_20260709_213934.png)

This page is looking normal but when we see source code carefully We can see that in the head section the page is calling background.png in <style> header

![image](/Hackerone-CTFs/assets/Screenshot_20260709_214046.png)

To further check about this navigate to the network tab and refresh the tab and you will see a request to get this image

![Network-tab](/Hackerone-CTFs/assets/Screenshot_20260709_214242.png)

To verify this request you can copy from network tab by right clicking on mouse and then press copy as curl or simply copy the url and use command

**curl https://4af587789c5e848f4b35004dcf477310.ctf.hacker101.com/background.png**

And you can see this returns the flag 

![Result](/Hackerone-CTFs/assets/Screenshot_20260709_214433.png)

## Lesson
Static page doesn't mean that the page is fully secure you can check source aur requests of this page and then try to manipulate requests that can be a great vector of attack
