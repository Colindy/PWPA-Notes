## Bypassing Input Validation and Encoding Techniques

You can try many different ways to try and bypass filters.

You can try a number of the following for different results.

```
<script>prompt(1)</script>
<img src=0 onerror=prompt(1)>
<scr<script>ipt>prompt(1)</scr</script>ipt>
```

You can also encode different characters if you see things that are being stripped out.  There are a number of options also in burpsuite to help with encoding.

You also have the docker lab to use.  The Input Validation lab can be used to test a number of these.