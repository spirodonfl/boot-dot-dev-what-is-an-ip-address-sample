#### What is an IP Address?

Any time you're typing an address into your browser like https://boot.dev, what you're saying is something like:

Let's go to Boots house!

Any time you're typing an IP address into your browser like https://104.123.67.49, what you're saying is something like:

Let's go to 90210 Beverly Hills, California, USA ... 's house!

You can prove this with some simple code, using Node.js

Assignment: enter a URL of your choice on line 5

```
// require dns module
const dns = require("dns");

// website URL (Boots house!)
const url = "google.com";

// get the IPv4 address
// using dns.resolve4() function
dns.resolve4(url, (err, addresses) => {
  if (err) {
    console.log("ERROR", err);
    return;
  }

  console.log(addresses);

  // eg: 64.233.191.113
  // like 90210 Bevery Hills .... 's house
});
```

##### References for this lesson

* https://nodejs.org/api/dns.html
* https://ca.norton.com/blog/privacy/what-is-an-ip-address
* https://en.wikipedia.org/wiki/IP_address

#### URLs are IPs in EZ mode

The last lesson demonstrated that URLs are just a way for you to give yourself a break and not remember all the numbers that make up an IP address.

But, that means *someone* has to remember Boots address. If you type in https://boot.dev in your browser, *you* may not need to remember the address.

So who does?

Your internet service provider can figure this out for you.

In no small part, things called "nameservers" play a role in this. They help to "resolve" an address to an IP and all internet service providers generally talk to each other in this (and several other) methods.

This is sort of like looking up a map with a general idea of where Boots house is and then getting some directions to the right address. Sort of. Except this map knows the address of whatever person you're asking for.

We can test this with some code too!

Again, like last time, enter a URL of your choice in line 4. Make note of the nameservers that are returned.

```
// require dns module
const dns = require("dns");

// website URL (Boots house!)
const url = "google.com";

dns.resolveNs(url, (err, nameservers) => {
  if (err) {
    console.log("ERROR", err);
    return;
  }

  console.log(nameservers);
});
```

##### References for this lesson

* https://aws.amazon.com/blogs/mobile/what-happens-when-you-type-a-url-into-your-browser/
* https://en.wikipedia.org/wiki/Web_browser#:~:text=Virtually%20all%20URLs%20are%20retrieved,communications%20security%20and%20information%20privacy.

#### IPs generally follow a format

TODO: Fill this section out

```
[TODO: Code here where the IP address is formatted incorrectly and the user needs to find the right IP address and fix it using DNS && resolve from previous lessons]
```
##### References for this lesson

* https://simple.wikipedia.org/wiki/IP_address#:~:text=IP%20addresses%20are%20usually%20written%20in%20human%2Dreadable%20form%2C%20where,group%20of%20eight%20hexadecimal%20numbers.
* https://learn.microsoft.com/en-us/troubleshoot/windows-client/networking/tcpip-addressing-and-subnetting

#### IPs have doors

You show up to part at Boots house. You knock on the front door. Nobody answers. You call Boot and tell him you're here. He tells you to go around back, the back door is open.

These are ports. When you've reached an IP address, you are either denied or given access to ports (doors to the house) which then let you interact with whatever's inside.

```
[TODO: Code here to explicitly pass the 443 vs 80 ports on an IP address to get the same resulting output as doing https://somedomain.com vs http://somedomain.com]
```

TODO: Next lesson being the difference in ports in the URL (http vs https for example), thereby merging some of the previous lessons together yet again.
##### References for this lesson

* https://en.wikipedia.org/wiki/List_of_TCP_and_UDP_port_numbers
