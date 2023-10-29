# Aliens Make Me Wanna Curl

## Problem statement

We are expecting communications from an artificial intelligence device called MU-TH-UR 6000, referred to as mother by the crew. We disabled the login page and implemented a different method of authentication. The username is mother and the password is ovomorph. To ensure security, only mothers specific browser is allowed.

https://spooky-aliens-make-me-wanna-curl-web.chals.io/flag


# Solution

1. By reading the title, we can think that ```curl``` will be the command to use ;
2. The command used to get the flag is :
```curl -A 'MU-TH-UR 6000' -u mother:ovomorph https://spooky-aliens-make-me-wanna-curl-web.chals.io/flag```

The flag is : **NICC{dOnt_d3pEnD_On_h3AdeRs_4_s3eCu1ty}**
