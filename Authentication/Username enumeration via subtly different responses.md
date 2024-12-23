[Try it yourself before continuing](https://portswigger.net/web-security/authentication/password-based/lab-username-enumeration-via-subtly-different-responses)

![](./Images/Pasted%20image%2020241223053730.png)

---
In the login page we send `admin:admin` and send the request to intruder

![](./Images/Pasted%20image%2020241223055457.png)

Let enumerate username

![](./Images/Pasted%20image%2020241223055555.png)

![](./Images/Pasted%20image%2020241223055623.png)

We need to "grep" the `subtly` message

![](./Images/Pasted%20image%2020241223055803.png)

The result when we click on "ok"

![](./Images/Pasted%20image%2020241223055817.png)

Now start attack

we have the message `Invalid username or password` without  << **`.`** >>

![](./Images/Pasted%20image%2020241223055934.png)

Else we know the username, now enumerate the password by using the same technique

![](./Images/Pasted%20image%2020241223060003.png)

And you get the correct credentials. Login and resolve the lab

![](./Images/Pasted%20image%2020241223060041.png)

