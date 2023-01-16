# TetraCube Red Project

TetraCube is a project to make a home very smart.
This project doesn't rely only on IoT world, but is about my personal needs.

The goal of the project is to offer tailored features in only one app and with a single 
point of entry.

The project is founded on common and modern concepts:
* microservices
* external IdP service with OAuth authentication
* native mobile app built with Kotlin Native
* deployment on Kubernetes
* reactive and real-time programming

## Components of the project

The project is founded on three macro-groups os components:
* TMS CLI: TetraCube Management System CLI, a helper program that helps users to install 
the platform into target system
* identity Provider provided from keycloak
* a bunch of microservices, one for specific application feature
* an android mobile app

## How to install the project

### Prerequirements

Prepared a self-singed certificate.
This kind of certificate is important to be sure that each private installation has its own
private certificate and is not possibile to decrypt someone's messages.

```shell
openssl req -newkey rsa:2048 -nodes   -keyout keycloak-server.key.pem   -x509 -days 3650   -out keycloak-server.crt.pem
```

some data will be requested in form of interactive fields

```shell
You are about to be asked to enter information that will be incorporated
into your certificate request.
What you are about to enter is what is called a Distinguished Name or a DN.
There are quite a few fields but you can leave some blank
For some fields there will be a default value,
If you enter '.', the field will be left blank.
-----
Country Name (2 letter code) [XX]:
State or Province Name (full name) []:
Locality Name (eg, city) [Default City]:
Organization Name (eg, company) [Default Company Ltd]:TetraCube
Organizational Unit Name (eg, section) []:
Common Name (eg, your name or your server\'s hostname) []:<Set hostname same set in SOLUTION_HOSTNAME setting in .env file>
Email Address []:<your email>
```