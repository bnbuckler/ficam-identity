---
layout: page_collection
title: Core Identity Attributes
collection: plan
permalink: plan/id-attributes/
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
-----------------------------------------------

An agency typically collects a wide variety of data elements about its users. Within this data set, smaller subsets of attributes enable an agency to uniquely identify an individual within the organization and supports execution of meaningful access control decisions. This data set is known as the core digital identity. A key enabler for agencies to align with the FICAM architecture for core digital identities is the development of a common government-wide Core Person Model, intended to manage and share digital identity records.

The ICAM Subcommittee developed the government-wide Core Person Model for use by agencies working to align with the FICAM architecture. As shown in the table below, the Core Person Model provides a common definition for the attributes that comprise a digital identity record within the Federal Government. 

<br>

| <center> Attribute </center> | <center> Description </center> |
| :---------------------------:|--------------------------------|
| **Person Identifier** | Uniquely identifies an individual within a specified domain in which the person exists (e.g., Locally Unique Identifier [LUID] associated with the Backend Attribute Exchange [BAE]) |
| **Name** | An individual's name, typically including first, middle, last, and display names |
| **_Set of_ Biometrics** | A measured biological or behavioral characteristic of an individual (e.g., electronic fingerprint template, facial image) |
| **Physical Description** | An individual's physical characteristics (e.g., height, eye color, hair color, sex) |
| **Birth Record** | Pertains to the place (city, state, and country) and date of a person's birth record |
| **Contact Information** | Includes an individual's phone number(s) and work mailing address |
| **_Set of_ Credentials** | Relates to one or more identity credentials possessed by an individual (e.g., credential sponsor, FASC-N, serial number(s), issuer, revocation uniform resource identifier [URI], etc.) |
| **_Set of_ Citizenships** | An individual's country or countries of citizenship, commonly expressed as a digraph or trigraph |
| **_Set of_ Email Addresses** | An individual's current and historical email addresses |
| **_Set of_ Clearances** | An individual's background investigation and/or clearance history (e.g., investigation type, completion date, status, etc.)|
| **_Set of_ Affiliates** | An individual's affiliation with an organization (e.g., employee status, business relationship, etc.)|
| **Social Security Number (SSN)** | An individual's SSN or other national ID with a corresponding country code for foreign nationals |

<br>

The attributes identified in the Core Person Model are intended to serve as a baseline. It is expected that agencies may need to supplement the model with additional attributes that support the agency's mission-specific business needs. An agency should work to streamline and consolidate the processes for storing and managing them wherever possible. 

In order to fully leverage the Core Person Model, an agency should consider the following: 

* **Identify where each data element is collected and stored.** Agencies should determine where each attribute is located and determine which offices or groups are responsible for collecting and maintaining those data elements.
<br>
<br>
* **Map agency data to the model.** After identifying the location of each data element, an agency should map its data model to the Core Person Model to tailor it for agency use.
<br>
<br>
* **Determine additional core data elements, if necessary.** If additional attributes are necessary to support the implementation of the Core Person Model, they should be limited to those elements that are needed to uniquely identify an individual within the organization and support the agency's specific mission needs. Additional identity attributes may be collected to support enhanced access control scenarios, but these are considered entitlement attributes, not part of the basic digital identity record.
<br>
<br>
* **Identify opportunities for process integration.** Agencies should identify redundancies in data collection associated with the Core Person Model and determine opportunities to integrate and streamline these business processes by leveraging existing identity data.
<br>
<br>

Managing a digital identity at an enterprise level by leveraging core digital identities can provide agencies with a number of benefits, including:

* **Eliminating redundant identity data creation.** Agencies are able to reduce or eliminate the need for excess business processes that may collect redundant identity data for specific application use.
<br>
<br>
* **Enabling interoperability and more robust identity attribute sharing.** Agencies are provided with a common basis for sharing identity attributes internally. When combined with the establishment of attribute management and distribution services, agencies are able to offer enhanced attribute sharing capabilities for use by programs and applications across the organization.
<br>
<br>
* **Streamlining identity life cycle management.** The administrative burden associated with identity life cycle management is greatly reduced, while improving data quality and accuracy.
<br>
<br>
* **Increasing the accuracy and reliability of provisioned identities.** Provides consistency across enterprise identities and improves the accuracy of user account data established through automated provisioning workflows.













































