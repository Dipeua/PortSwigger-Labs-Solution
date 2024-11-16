[Try it yourself before continuing](https://portswigger.net/web-security/nosql-injection/lab-nosql-injection-detection)

![](./Images/Pasted%20image%2020241116072516.png)

---
After enumeration we found The category filter and the Normal Request gives us 03 products

![](./Images/Pasted%20image%2020241116073553.png)

![](./Images/Pasted%20image%2020241116073645.png)

Now that we know the normal behavior of the request, let's try to Detect NoSQL injection vulnerabilities by trying to break the query syntax.

We need to determine which characters are interpreted as syntax by the application

By submitting special characters that will trigger an error or any other detectable behavior.

![](./Images/Pasted%20image%2020241116073945.png)

If we look more closely

![](./Images/Pasted%20image%2020241116074033.png)

> Since this resulted in a change from the original answer, this indicates that the character `'` broke the query syntax and caused a syntax error.

This can be confirmed with `\'`

> If this does not cause a syntax error, it may mean that the application is vulnerable to an injection attack.

![](./Images/Pasted%20image%2020241116074528.png)

![](./Images/Pasted%20image%2020241116074549.png)

This did not cause any syntax error so the application is vulnerable

The next step is to determine if we can influence the boolean conditions by sending two queries true and false

![](./Images/Pasted%20image%2020241116075319.png)

![](./Images/Pasted%20image%2020241116075341.png)

As the application behaves differently from 02 requests, then injecting this style of syntax impacts a server-side request.

Now that we have identified that we can influence boolean conditions, we can attempt to override the existing conditions to exploit the vulnerability.

![](./Images/Pasted%20image%2020241116075645.png)

![](./Images/Pasted%20image%2020241116075721.png)
