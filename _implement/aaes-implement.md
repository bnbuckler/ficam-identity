---
layout: page_collection
title: AAES Implementation Considerations
collection: implement
permalink: implement/aaes-implement/
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
--------------------------------------------------------------

Deploying an AAES capability requires considerable planning, support, and coordination from various groups with an agency. Specific planning and coordination considerations include the following:

<br>

<div id="accordion" markdown="1">

### Data Quality
<div markdown="1">

Identity data needs to be stored in a consistent and defined format prior to implementing the AAM and must be up-to-date. If the quality of data is poor going into the AAES, then the data shared from the AAES will also be poor quality.

</div>

### Defining Identities
<div markdown="1">

If there are multiple sources of identity attributes, the AAM should be able to determine which source is authoritative and be used to define the digital identity.

</div>

### Flexible Authoritative Attribute Source Selection
<div markdown="1">

Many agencies don't have a central location to create, update, and store all attributes used throughout the agency. Therefore, if there are conflicting values from different sources for the same attribute, it is important to develop a process for identifying and selecting the most accurate value. These processes may range from identifying which record was most recently updated to comparing multiple sources and selecting the value which appears most often.

</div>

### Correlation of Identity Attributes
<div markdown="1">

Given the number of potential sources for identity attributes, an agency should determine a mechanism for correlating those attributes into a single digital identity within the Attribute Manager. That is, each individual needs to be uniquely identified and attributes of the same identity from different sources should be correlated to the same digital identity. Attributes can be correlated using a unique person identifier or a combination of attributes (i.e., a multi-attribute key). If a reliable correlation key doesn't exist, a mechanism must be developed for accurately correlating identity information, perhaps involving human review of potentially conflicting records.

</div>

### Normalization
<div markdown="1">

Normalization creates a common and consistent classification for attributes. It provides a mapping between different attribute types and values. For example, one bureau/component's organization attribute can be equivalent to another's division attribute. Establishing a process for normalizing these attributes (e.g., data modeling) across an agency is critical to enabling effective attribute sharing.

</div>

### Reconciliation of Identity Attributes
<div markdown="1">

While correlating attributes to an identity, different authoritative sources may have different or missing data regarding the same identity attribute. A process needs to be put in place to correct the differences and store the correct attribute in the AAM. This often requires manual review of the attributes. The problem also needs to be fixed upstream, which can be achieved by creating a data scanning tool to check for error conditions before populating the AAM. Another option would be to build a process to notify the appropriate personnel to correct the source data manually.

</div>

### Sensitivity of Data
<div markdown="1">

Due to the sensitivity of identity data, it is extremely important to ensure that proper access controls are in place. The various tools used to implement an AAES can provide enhanced security and privacy for an individual's PII. For example, specific views can be created based on a user's role to limit access to sensitive data elements. This can be a good method to satisfy users with different reporting requirements while protecting sensitive data from those who a lack a need to know it.

</div>

### Securing the AAES
<div markdown="1">

Access controls alone are not sufficient protection, so other security processes should be put in place to protect the AAES, including: 

* Ensuring traffic travels through firewalls to filer application and network layer attacks
* Protecting data with encryption while at rest and during transit
* Using a logging tool that will allow for periodic security audits
* Using monitoring tools to ensure the integrity of the AAES hasn't been compromised

</div>

### Access to the AAES
<div markdown="1">

The requesting party should never have direct access to the attributes contained within the AAM component of the AAES. It is expected that the majority of attribute consumers will be other agency IT applications that will obtain attributes from the AAD based on a defined attribute agreement or MOU. This is recommended because it makes it harder attackers to access the Attribute Manager by not knowing the true address of the Attribute Manager. 

</div>

### Access Control Groups
<div markdown="1">

To streamline the process of interfacing with the AAES, attributes can be grouped based on sensitivity (e.g., public, confidential, confidential PII) or business level roles (e.g., HR, benefits administration, access control administration, etc.). Groups of attributes can then be requested based on the need and usage criteria.

</div>

### Integration into System Development Life Cycle (SDLC)
<div markdown="1">

An agency should consider adding a step into its SDLC to ensure that new applications consider how to integrate with and use the AAES. This may involve providing a standard method for requesting applications to provide justification, get approved, and sign a governance agreement for receiving the data. It may also involve establishing a process for quickly creating new access control groups and/or attribute views as they are requested.

</div>

### Push vs. Pull
<div markdown="1">

Pulling data refers to consumers requesting data using the AAD's service layer. Pushing data refers to the AAD sending data back to authoritative sources and downstream applications. Both pushing and pulling of data should be accounted for during implementation in order to accommodate the varying capabilities of legacy systems that will consume the attributes. 

</div>

### Use of Attribute Service for More Than Identity
<div markdown="1">

While the scope of this section has focused on identity attributes, a similar architecture (or the same AAES) can be used or expanded upon to include entitlement attributes.

</div>

### Governance of Attribute Sharing
<div markdown="1">

Agencies should consider establishing guidelines to protect against unauthorized disclosure of identity information. This include establishing an attribute agreement or MOU to define which attributes will be made available to specific attribute consumers via the AAES. Taking this step ensures that attribute consumers are provided with the information necessary to effectively make authorization decisions while limiting the exposure of unnecessary information. 

</div>












