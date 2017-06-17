# StatiCrypt

Based on the [crypto-js](https://github.com/brix/crypto-js) library, StatiCrypt uses AES-256 to encrypt your string with your passphrase in your browser (client side).

Download your encrypted string in a HTML page with a password prompt you can upload anywhere (see [example](https://robinmoisson.github.io/staticrypt/example.html)).


## HOW IT WORKS

StatiCrypt generates a static, password protected page that can be decrypted in-browser: just send or upload the generated page to a place serving static content (github pages, for exemple) and you're done: the javascript will prompt users for password, decrypt the page and load your HTML.

**Disclaimer** TL;DR: if you have extra sensitive data you should probably use something else :)

StatiCrypt basically encrypts your page and puts everything with a user-friendly way to use a password in the new file. 

AES-256 is state of the art but brute-force/dictionnary attacks are trivial to do at a really fast pace: use a long, unusual passphrase!

The concept is simple but this is a side project - not purporting to be bulletproof, feel free to contribute or report any thought to the GitHub project !

## Improvements and development

Browsers don't like to work with local files.

But it's easy enough to run a simple server, for example,

```
$ ruby -rwebrick -e'WEBrick::HTTPServer.new(:Port => 8000, :DocumentRoot => Dir.pwd).start'

Then open http://localhost:8000 in your browser.

Or 

```
$ python3 -m http.server 8000
