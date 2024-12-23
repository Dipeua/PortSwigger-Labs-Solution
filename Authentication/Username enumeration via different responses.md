[Try it yourself before continuing](https://portswigger.net/web-security/authentication/password-based/lab-username-enumeration-via-different-responses)

![](./Images/Pasted%20image%2020241223050801.png)

---
In the login page we send `admin:admin`

![](./Images/Pasted%20image%2020241223050920.png)

Now send the request to intruder

![](./Images/Pasted%20image%2020241223051722.png)

Let enumerate username

![](./Images/Pasted%20image%2020241223051635.png)

we have the message `Incorrect password` that means `atlanta` is the correct username 

![](./Images/Pasted%20image%2020241223051528.png)

Now enumerate the password by using the same technique

![](./Images/Pasted%20image%2020241223051942.png)

And you get the correct credentials. Login and resolve the lab

