[Back to Home](../README.md#security)
# SSL
SSL (Secure Sockets Layer) is a security protocol 
that provides a secure and encrypted connection 
between a web server and a web browser. 
It was developed by Netscape in the mid-1990s 
and has since been widely adopted for securing 
online transactions, such as e-commerce, online banking,
and other sensitive data transfers.

The SSL protocol uses a combination of public-key 
and symmetric-key encryption to ensure the 
confidentiality, integrity, and authenticity 
of data transmitted over the internet. 
When you visit a website with SSL enabled, 
your web browser and the web server exchange 
digital certificates to verify their identities 
and establish a secure connection.

The SSL protocol has since been replaced by the newer
TLS (Transport Layer Security) protocol,
which is essentially an updated version of SSL. 
TLS provides the same security features as SSL 
but is more secure and efficient.

To enable SSL/TLS on a website, the website owner 
needs to obtain an SSL/TLS certificate from a trusted
Certificate Authority (CA). This certificate contains 
information about the website owner's identity, 
the website's domain name, and the public key needed 
for encryption.

Once the SSL/TLS certificate is installed on the web 
server, any data transmitted between the web server 
and the web browser is encrypted and secure from
interception by third parties. This helps to protect 
sensitive data such as credit card numbers, passwords,
and other personal information from being stolen or 
tampered with during transmission over the internet.

In summary, SSL/TLS is an essential security protocol 
for ensuring the privacy and security of online transactions, 
and is widely used to protect sensitive data on the internet.

# TLS
TLS (Transport Layer Security) is a cryptographic 
protocol designed to provide secure communication
over a network, typically the internet.
It is the successor to the SSL (Secure Sockets Layer)
protocol and provides a secure channel for data
transmission between two endpoints, such as a web browser 
and a web server.

TLS uses a combination of symmetric-key cryptography 
and public-key cryptography to provide encryption, 
integrity, and authentication of data transmitted
between two endpoints. When a TLS connection is established,
the client and server negotiate a shared secret key
that is used to encrypt and decrypt the data. 
This ensures that the data transmitted over the network 
is protected from eavesdropping, tampering, and forgery.

TLS is used to secure a wide range of applications, 
including web browsing, email, instant messaging, 
and file transfer. It is an essential component 
of modern internet security, and many websites and 
online services rely on it to protect their users' 
sensitive information.

# SSL/TLS FAQ
## What is SSL/TLS?
SSL/TLS stands for Secure Sockets Layer/Transport 
Layer Security. It is a protocol used to provide
secure communication over the internet.

## What is the difference between SSL and TLS?
SSL and TLS are two different protocols that are used
to provide secure communication over the internet. 
SSL was developed by Netscape in the 1990s and TLS 
is its successor. TLS is technically an updated version
of SSL, but the terms are often used interchangeably.

## What is the purpose of SSL/TLS?
The purpose of SSL/TLS is to provide a secure and encrypted
communication channel over the internet. This is important
for protecting sensitive information such as login credentials,
financial transactions, and personal data from being 
intercepted or manipulated by malicious actors.

## How does SSL/TLS work?
SSL/TLS works by establishing a secure connection between 
a client and a server using a combination of symmetric and
asymmetric encryption. The client and server negotiate which
encryption algorithm to use, exchange encryption keys, 
and then use those keys to encrypt and decrypt data 
transmitted between them.

## What is an SSL/TLS certificate?
An SSL/TLS certificate is a digital certificate that 
is used to verify the identity of a website and to encrypt
data transmitted between a client and a server. 
It contains information such as the website owner's name 
and public key, and is issued by a trusted third-party 
certificate authority.

## What is a certificate authority?
A certificate authority is a trusted third-party organization
that issues SSL/TLS certificates. They are responsible 
for verifying the identity of the certificate holder
and ensuring that the certificate is valid.

## What is a self-signed certificate?
A self-signed certificate is a certificate that is generated
and signed by the website owner rather than a trusted third-party
certificate authority. They are not recommended for use on 
public-facing websites as they do not provide the same level 
of trust and security as certificates issued by a trusted
certificate authority.

## What is HTTPS?
HTTPS stands for Hypertext Transfer Protocol Secure.
It is the secure version of HTTP, the protocol used for
transmitting data over the internet. HTTPS uses SSL/TLS 
to encrypt data transmitted between a client and a server,
providing an extra layer of security.

## What is a man-in-the-middle attack?
A man-in-the-middle attack is a type of cyberattack in which 
an attacker intercepts communication between two parties and 
is able to view and manipulate the data being transmitted.
SSL/TLS is designed to prevent man-in-the-middle attacks 
by encrypting data and verifying the identity of the communicating
parties using digital certificates.