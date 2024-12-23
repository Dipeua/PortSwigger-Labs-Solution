[Try it yourself before continuing](https://portswigger.net/web-security/authentication/password-based/lab-username-enumeration-via-response-timing)

![](./Images/Pasted%20image%2020241223072901.png)

---

In the login page we send `admin:admin`

![](./Images/Pasted%20image%2020241223082443.png)

![](./Images/Pasted%20image%2020241223082452.png)

Notice that our IP will be blocked if you make too many invalid login attempts (3 times)

![](./Images/Pasted%20image%2020241223082519.png)

Bypass IP protection using `X-Forwarded-For` header

![](./Images/Pasted%20image%2020241223082653.png)

We can see we can do many request by modifier the value of the new header

let try valid username

![](./Images/Pasted%20image%2020241223082748.png)

> Response time is increased depending on the length of the password you entered.
> to confirm we send again but whit a big contain on password param

![](./Images/Pasted%20image%2020241223082849.png)

Send this request to Burp Intruder

![](./Images/Pasted%20image%2020241223082944.png)

> Notice that one of the response times was significantly longer than the others. 

![](./Images/Pasted%20image%2020241223083216.png)

to make sure it consistently takes longer, let repeat the request 

![](./Images/Pasted%20image%2020241223083413.png)

Create a new Burp Intruder attack for the same request. Add the `X-Forwarded-For` header again and add a payload position to it. Insert the username that you just identified and add a payload position to the `password` parameter.

![](./Images/Pasted%20image%2020241223083505.png)

When the attack is finished, find the response with a `302` status.

![](./Images/Pasted%20image%2020241223083716.png)

Log in using the username and password that you identified and access the user account page to solve the lab.
