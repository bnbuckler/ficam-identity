---
layout: page_collection
title: Authoritative Attribute Exchange Service
collection: overview
permalink: overview/2_ae-elements/
---
<script>
$(function() {
  $( "#accordion" ).accordion({
    heightStyle: "content",
    collapsible: "true",
    active: "false"
  });
});
</script>
---------------------------------------------

Agencies have a common need to collect and share basic identity data within their organization to support credential issuance, provisioning of user accounts, and access control administration. The ICAM Services framework introduces an Authoritative Attribute Exchange Service (AAES) capability as the means to securely share authoritative identity attributes within an agency. An AAES is a technical solution that gives agencies the ability to connect various authoritative data sources and share identity and other attributes with the shared enterprise infrastructure. 

The AAES capability allows agencies to link their authoritative sources of identity information with customers of identity data across the agency, eliminating the need to redundantly collect identity data at each point where it is used.

When seeking to electronically share attribute data between authoritative source systems and relying parties, there are three core elements that must be addressed to support the attribute exchange:

* **Protocol** - The technical means by which identity attributes are exchanged. The attribute provider and relying party involved in the exchange must agree upon the procol that will be used.
* **Payload** - The digital identity attributes that are exchanged between the parties; typically involves attribute contracts to define what is included and how it is formatted.
* **Policy** - The governance processes and mechanisms that are put into place to manage and operate the exchange and adjudicate any issues that may arise.

Each of these core elements are discussed in greater detail below, providing guidance on aligning attribute exchange capabilities with the FICAM architecture and the processes and requirements associated with the Federal Trust Framework.

<br>

### Protocol

Defining a common exchange protocol enables the involved parties to communicate using the same language and set of rules. When establishing an attribute sharing capability, an agency should select a protocol that meets the technical operational needs of both the Identity Provider and Relying Party. Selecting an appropriate protocol is also dependent on the type of connection that is desired between the parties, as different types of connections may not be equally supported by all approved protocols.

The table below contains a sampling of several common protocols used for exchanging identity data.

<br>

| <center> Protocol </center> | <center> Description </center> |
|:---------------------------:|------------------------------------------|
| **LDAP/s** | Lightweight Directory Access Protocol is used to read and/or edit directories. Traffic to and from the directory should be encrypted (i.e., TLS, SSL, Internet Protocol Security). Access control should be in place to ensure data is provided to only those authorized to view it. |
| **DSML** | Directory Service Markup Language provides directory service information in an XML syntax. Data traverses across HTTP/s. |
| **SAML**| Security Assertion Markup Language is used to exchange authentication and authorization data in XML. |
| **SPML**| Service Provisioning Markup Language is an open standard that uses an XML-based framework for the integration and interoperation of service provisioning requests. |

<br>

### Payload

A critical component of any identity attribute exchange capability involves defining what attributes will be exchanged between the parties and how those attributes will be formatted. Defining attribute syntax (e.g., format) helps ensure that identity attributes are received in such a manner that they are usable within a relying party application. This is typically accomplished by establishing an attribute contract.

When streamlining the exchange and management of identity data within an agency, it is expected that the payload will align with the government-wide Core Person Model. However, an agency may opt to include additional attributes based on its specific mission and business needs.

<br>

| <center> Terminology </center> | 
|---------------------------------|
| **Attribute Contract** - A document that extensively describes the agreement on the set of, and syntax of, attributes that members of a federation have to abide by on the payload. |

<br>

### Policy

Establishing governance is important to maintaining the ongoing operation of identity attribute sharing arrangements and providing a framework to help ensure that both the Identity Provider and Relying Party(s) operate within the confines of the arrangement. An agency implementing an internally-focused attribute sharing capability should establish agency policies governing the appropriate use of identity data that is made available through the solution. This can often alleviate the need for point-to-point agreements between groups within the organization.

<br>

| <center> Privacy Tip </center> |
|--------------------------------|
| Implementing an attribute sharing capability provides an agency with a number of benefits and process efficiencies. However, one goal of this effort is to avoid collecting and/or sharing more PII than is necessary for the intended use. Therefore, only those attributes that are necessary should be shared with a relying party. To achieve this, agencies should consider establishing attribute agreements or attribute practice statements to address which attributes will be shared and the manner in which they will be conveyed, to ensure privacy and security. |











 

























