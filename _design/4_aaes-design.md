---
layout: page_collection
title: AAES Common Design Characteristics
collection: design
permalink: design/4_aaes-design/
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
---------------------------------------------------------

In order to successfully build and deploy an AAES capability, it is necessary to understand the common characteristics that the solution should include in order to meet the objectives of the FICAM architecture. These common characteristics are identified in the table below are identified in the table below. However, it is also important for agencies to consider their specific needs when designing an AAES.

<br>

| AAES Characteristic ID | <center> AAES Solution Characteristics </center> |
|:-----------------------------------------:|------------------------|
| **AAES 1** | Provides aggregation of identity attributes |
| **AAES 2** | Supports deployment of connectors and service interfaces to retrieve identity attributes for distributed sources |
| **AAES 3** | Uses a unique person identifier to distinguish between identities |
| **AAES 4** | Provides transformation of identity attributes from authoritative source data storage format to a standardized format to present data externally |
| **AAES 5** | Provides correlation of identity attributes from distributed sources of identity information |
| **AAES 6** | Provides the capabiltiy to reconcile differences between different sources of identity attributes | 
| **AAES 7** | Provides an interface to request identity attributes over common protocols, such as LDAP/s, DSML, SAML, and SPML |
| **AAES 8** | Provides security to protect data against unauthorized access and logging to facilitate audits |
| **AAES 9** | Provides various views of identity attributes and display them only to users or systems that are authorized to view those attributes |
| **AAES 10** | Provides the ability to request identity data based on a variety of methods (name, globally unique identifier, email, DOB) |
| **AAES 11** | Provides reports of identity attributes | 
| **AAES 12** | Provides the capability to push or pull identity attributes, including the ability to distribute new identities and updates to existing identity attributes |
| **AAES 13** | Provides the capability to protect data at rest |
| **AAES 14** | Provides the capability to sign attribute assertions |




















