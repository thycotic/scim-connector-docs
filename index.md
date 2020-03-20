[title]: # (SCIM Connector)
[tags]: # (introduction)
[priority]: # (1)
# Introduction

The Thycotic *System for Cross-Domain Identity Management* (SCIM) connector is a Web application that can be installed on a server machine, which exposes SCIM-defined endpoints and *Secret Server* (SS) APIs. The SCIM connector translates user, group and privilege access management information into SCIM-defined *JavaScript Object Notation* (JSON) responses. The Web application enables any SCIM endpoint to interact with SS using a well-defined standard method.

## What is SCIM?

SCIM is an open standard that allows you to automate user provisioning using a *Representational State Transfer* (REST) API and JSON. The SCIM specification (RFC7643) provides schemas that represent common identity information about users and groups. See the [SCIM Specification](http://www.simplecloud.info/?elqct=Website&elqchannel=OrganicDirect%23Specification) for more information about SCIM.

## SCIM Extension Support

*Privileged Access Management* (PAM) software typically makes use of common user and group models, as well as defining additional constructs, to provide fine-grained authorization and management for privileged access. The [SCIM 2.0 Extension for PAM](https://tools.ietf.org/html/draft-grizzle-scim-pam-ext-00)
includes extensions to the core user and group objects and new resource types and schemas for standard PAM constructs. This extension is intended to provide greater interoperability between PAM software and clients, a common language for PAM concepts, and a baseline that can be further extended to support more
complex PAM requirements.
