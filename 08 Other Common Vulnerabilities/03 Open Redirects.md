## Open Redirects

Here you're looking for partial URLs inside the full URL.

For example, here we have a URL that has a partial URL at the end labeled `return_url`.  We can manipulate this to send the user to any site we want to.

For example, if we change the follow...

`http://localhost/labs/r0x01_script.php?id=1&return_url=./r0x01.php`

to the following...

`http://localhost/labs/r0x01_script.php?id=1&return_url=https://www.google.com`

when someone clicks on the "Return" button, they are taken to whatever site we put in (in this case, google.com).
