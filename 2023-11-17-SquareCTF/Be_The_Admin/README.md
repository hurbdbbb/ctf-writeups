# Be the Admin

## Problem statement

This website is a forum where people can make posts, though it's so broken right now that you can probably only search them. It turns out that someone posted something top secret and later deleted it, but was it truly deleted?
http://184.72.87.9:8013

## Solution

Here is the home page of the website :

![home_page](https://github.com/Pink-Balloon-Eternal/ctf-writeups/assets/78924080/6a3e1f73-4e63-467a-8232-985fb77931c4)

By going to the CTF Participant web page we have this :

![CTF_participant_page](https://github.com/Pink-Balloon-Eternal/ctf-writeups/assets/78924080/2d8a0900-a765-48e5-af9b-237ef378def2)

And by going to the Admin web page we see this :

![admin_page](https://github.com/Pink-Balloon-Eternal/ctf-writeups/assets/78924080/ed261657-093c-4c6e-8460-acab9ddd331c)

According to the problem statement and what we can see on the website, we could think that the flag is the secret of the Admin and that we have to be the admin to see the secret. But how ?
We have not an authentification system or something of that kind. After some research, the solution could be our session cookie : "Q1RGIFBhcnRpY2lwYW50".
By passing the session cookie into a base64 decoder, we observe that its says : "CTF Participant". Eureka! We have to change our session cookie to be the admin.

By encoding "Admin" into a base64 string, we get : "QWRtaW4"
We changed the session cookie with this value and refreshed the Admin page. The web page now shows the flag :

![flag](https://github.com/Pink-Balloon-Eternal/ctf-writeups/assets/78924080/bc9d15f6-9db5-47ba-9e41-df9085d14f63)

Flag : **flag{boyireallyhopenobodyfindsthis!!}**
