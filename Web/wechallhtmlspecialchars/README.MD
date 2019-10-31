Wechall htmlspecialchars

>Is to exploit this line of code, which is vulnerable to XSS:
GeSHi`ed PHP code for htmlspecialchars.php
1
echo "<a href='http://".htmlspecialchars(Common::getPost('input'))."'>Exploit Me</a>";
Common::getPost only fetches a string from the $_POST variables and applies stripslashes(), in case magic_quotes_gpc() are enabled.
You can ignore Common::getPost completely, replace it by $_POST['input'], and assume magic_quotes_gpc() are disabled.
Below the input box is the output of the script, to test your attacks.
You will fail anyway, because I used htmlspecialchars() to prevent XSS.
Gizmore - March, 23th 2009
