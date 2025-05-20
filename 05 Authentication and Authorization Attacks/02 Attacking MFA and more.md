### Attacking MFA

One way we can attack MFA is to make sure it's set up correctly.  It never hurts to just try and submit without MFA even if the page asks for it.  You might still get in if the config on the MFA is not correct.

You might also intercept the packet submitting the MFA code and change the username and see if that will let you into that other users account.


#### Spraying

You may come up on times where you know the accounts have a lockout threshold and you don't want to break that.  You can take the top couple known passwords and run them against a list of usernames that could be relevant.  We can also do this with `ffuf`.

Again, save the capture and edit the 2 points with distinct names.  FUZZUSER and FUZZPASS for example.

`ffuf -request req2.txt -request-proto http -mode clusterbomb -w /user/list.txt:FUZZUSER -w /password/list.txt:FUZZPASS`

In this one, you may look at outputting (`-o filename.txt`) it to a txt file and then grepping through it.  Since you don't want to lock accounts, you need your first shot to give you the info.  You likely could also copy and paste.  With a short list, you can just check through the list.

Also check out https://appsecexplained.gitbook.io/