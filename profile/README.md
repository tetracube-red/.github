# TetraCube Red Project

TetraCube is a home and life helper.
This project doesn't rely only on IoT world, but is built around my personal needs.

The goal of the project is to offer tailored features in only one app and without any particular "intelligent" feature. The target of this project is make easy the management of certain aspects of the home life where, sometimes, the helps suppliend from other applications are useless and make noise.

## Technology aspect

The project is founded on common and modern concepts, these are not adopted only for a sort of trend, but are useful to make the project maintainable.

* microservices architecture: in this way is possibile to create new features without touching anything of the existing system;
* external IdP service with OAuth authentication: in this way is possibile to create new feature and give access only to certain kind of guests;
* native mobile app built with Kotlin Native: modern declarative approach to build mobile UI;
* deployment on Kubernetes: is possibile to replicate and scale the applications fast and, in a far feature, deploy the system on a cloud system;
* reactive and real-time programming: each microservice will be able to scale along the requests without wasting resources, in the same time - with realtime approach - each guest have realtime updates about it's house state.

## Components of the project

The project is founded on three macro-groups os components:
* TMS CLI: TetraCube Management System CLI, an helper program that helps houseolder to:
    1. install the platform in the target system
    2. grant access to new guests
    3. renew access to the existing guests    
* the identity Provider provided from keycloak that tracks guests accesses
* a bunch of microservices, one for specific application's feature
* an android mobile app

## How to install the project

### Prerequirements

The application needs some step to be installed. Is not possibile to automate these steps because each target system and eache user has different kind of requirements and starts from a different initial conditions.

Here a list of requirements needed to install the platform:
1. An SSL certificate (self signed or trusted) -> see below to check how to generate a self signed certificate;
2. A phisical path in a node of the k8s cluster where store data of the database;

#### Prepare a self-singed certificate (Optional - Skip if you have another kind of certificate)

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

### Let's go to install!
Now is possibile install the application, so please refer the [TMS CLI Readme](https://github.com/tetracube-red/tms-cli/blob/main/README.md) to know how to use the CLI to install the platform.