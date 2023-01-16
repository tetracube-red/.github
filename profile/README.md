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

## Components of the project

The project is founded on three macro-groups os components:
* TMS CLI: TetraCube Management System CLI, a helper program that helps users to install 
the platform into target system
* identity Provider provided from keycloak
* a bunch of microservices, one for specific application feature
* an android mobile app

## How to install the project