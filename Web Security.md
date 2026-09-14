---
created: 2026-08-23T23:20
updated: 2026-08-23T23:20
---
**TLS/SSL:** Transport Layer Security/ Secure Sockets Layer
 happens btw http and tcp
 **Diffie-Hellman:**
 both client and server agrees on 2 numbers a,b, 
 clients -> selects one private key p1 prime number. client does a^p1 mod b = lets say r1, sends r1 to server, receives r2 does r2^p1 mod b
 server does-> its own private number p2, a^p2 mod b = r2, send r2 to client, receives r1 does-r1^p2 mod b
takes one more step by using ECDHE-> means uses fresh prime numbers for each connections => this property is forward secrecy

now to prove the authentication of the server we need ssl cert:
it contains: public key, domain, and authorized signature
certificate authority-> trusted 3rd party cmp eg-> let's encrypt and digicert
a list of certificate authority is pre populated in os 

signature verification Process:-
	Certificate signed by intermediate
	 Intermediate signed by trusted root
	 Domain matches domain name
![[TLS]]
