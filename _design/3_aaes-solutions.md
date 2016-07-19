---
layout: page_collection
title: AAES Solution Components
collection: design
permalink: design/3_aaes-solutions/
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
---------------------------------------------------------------------

This section describes the functionality and approaches for implementing the AAES Infrastructure components, the Authoritative Attribute Manager (AAM) and the Authoritative Attribute Distributor (AAD). 

In some cases, it may be possible to achieve the functionality described for both the AAM and AAD by implementing a single product or tool. Conversely, it is also possible that multiple products and/or purpose-built applications could be integrated to create a single AAES solution. Each agency should evaluate their existing and planned ICAM investments as well as the agency's infrastructure and select an implementation approach that best meets the business needs and mission requirements of the agency.

<br>

### Authoritative Attribute Manager

The Authoritative Attribute Manager (AAM) compares identity attributes from the various authoritative data sources within an agency and provides a single authoritative source of digital identity. The Manager acts as a central hub of attributes by combining data from the various sources through either resource connectors or web services. As a result, the Manager de-conflicts differences that exist in the same attribute between multiple sources.

While it would be ideal to define a single authoritative source for each identity attribute in the Core Person Model, it may not always be possible. For example, an agency may need to combine data from different HR systems for a single person. It may be necessary to further normalize the data to ensure that the various attributes are formatted in a way that they can be used by the applications and users that receive authoritative data through the AAES. The Attribute Manager is also capable of extending the schema for an identity, should there be a need for additional attributes that are not included in the implementation of the Core Person Model. 

By combining and comparing identity data in the Manager, attributes can be found in one location, improving consistency of data, as there is a single authoritative source. The Manager also provides an agency with the chance to support a number of enhanced capabilities, including support for multiple access control models at the application level that operate based on a variety of digital identity data elements.  This capability allows agencies to make more secure, accurate, and reliable access control decisions and enforce access controls at a much more granular level.

<br>

| <center> Lessons Learned </center> |
|------------------------------------|
| Treasury's PIV Data Synchronization solution includes a Data Management Service (DMS) that compares identity data from multiple authoritative sources and provides synchronization with relying systems. By making up-to-date identity data easily available to relying party systems, the DMS reduces redundant data collection and improves data accuracy throughout the agency. |

<br>

The AAM can be implemented in several ways, based on an agency's existing investments and infrastructure requirements, including:

* **Virtual Directory -** Combines and normalizes identity attributes, without the need to store them in a physical location, while also synchronizing attributes with authoritative data sources. When requested, the virtual directory searches the authoritative data sources and provides normalized attributes to the attribute consumer.

* **Metadirectory -** Similar to a virtual directory, in that it combines and normalizes identity attributes from multiple authoritative sources. However, it also involves physically storing the results of the data aggregation and synchronizing with the authoritative data stores in regular intervals.

* **Identity Manager -** The Identity Manager component of a modernized logical access control system (LACS) is capable of providing the identity attribute aggregation and normalization capabilities of the AAM. Agencies choosing to use an Identity Manager as part of their LACS modernization effort should prefer this approach in order to avoid redundant investment in this capability. 

<br>

| <center> Privacy Tip </center> |
|--------------------------------|
| When determining an appropriate approach to implementing an AAM, an agency should work with its Privacy Office to determine whether there is an existing Systems of Record Notice (SORN) in place or if a new SORN needs to be developed. The agency should also determine if a Privacy Impact Assessment (PIA) is required. If a new or updated PIA and/or SORN are necessary, then they must be in place before the approach can be developed and implemented. |

<br>

An agency should perform an analysis to determine which AAM option described above best meets its business needs and mission, while balancing the need to leverage existing investments. There are a number of benefits and limitations associated with each option that an agency should consider as part of its analysis. These benefits and limitations are outlined in the table below.

<br>

| <center> Approach </center> | <center> Benefits </center> | <center> Limitations </center> |
|-------------------------------------------------------------------------|
| **Virtual Directory** | •	Attributes are queried in real-time and results are dynamically provided to relying parties <br><br> • No requirement to physically store identity data eliminates privacy concerns associated with systems of record <br><br> • Ability to develop custom views for each relying party ensures that identity data is not shared inappropriately <br><br> • Ability to easily support a large number of authoritative data sources <br> • Data provided to consumer applications is always up-to-date with authoritative sources | • Dynamic querying places an additional performance load on authoritative source systems, but can be addressed through data caching <br><br> • Some authoritative data sources for identity data may not be built to support dynamic querying <br><br> • Pushing authoritative identity data to consumer applications requires an additional tool (Authoritative Attribute Distributor) <br><br> • AAES and consumer systems may be unable to pull data when the authoritative source is unavailable, but can be addressed through data caching |
| **Metadirectory** | • Minimal impact to performance authoritative data sources <br><br> • Queries by relying parties can be responded to faster due to local storage of data <br><br> • Minimally invasive to source systems that may have more complicates or proprietary data stores | • Data is physically stored locally, which is redundant with authoritative data sources and creates a new system of record <br><br> • Local data storage requires that appropriate security and privacy controls are in place <br><br> • May not be up-to-date with authoritative sources given synchronization schedule <br><br> • Pushing authoritative identity data to consumer applications requires an additional tool (Authoritative Attribute Distributor) |
| **Identity Manager** | • Opportunity to leverage an existing LACS investment <br><br> • Natively provides an ability to push identity data to consumers without the need for an additional component <br><br> • Streamlined integration with access control components <br><br> • Provides a number of enhanced capabilities, including provisioning, workflows to augment/enhance attributes, and user self-service | • Requires that agencies procure an Identity Manager (if one is not already owned) <br><br> • Some Identity Manager products may require that attributes be stored in a physical directory after aggregation |

<br>

Regardless of the implementation approach selected, an agency must appropriately protect the AAM due to the types and amount of data that it contains. To do so, an agency should ensure that agreements are in place to govern the exchange of identity attributes between these source systems and the AAM. 

<br>

### Authoritative Attribute Distributor

The AAM itself is not directly accessed by systems or humans that request attributes, rather it partners with the Authoritative Attribute Distributor (AAD). The AAD serves as the interface point for requesting applications. This provides an additional layer of security that prevents requesting parties from directly accessing the attributes, which could potentially lead to unauthorized disclosure. 

The Authoritative Attribute Distributor is designed to integrate with the AAM to provide attributes to consumer applications (i.e., applications that use identity data for downstream processes), both inside and outside the agency. The Distributor can also be used to synchronize user data with user accounts or local directories, based on the agency's requirements. The AAD serves as the primary communication point for consumer applications in that it both receives and responds to requests for attributes by pulling the appropriate attributes from the AAM. This capability provides applications with streamlined access to the attributes they requested while protecting the AAM (and its connected authoritative sources) from direct access from users and consumer applications, reducing the complexity of protecting the security and privacy of the data.

The AAD component can be the same product as the AAM. This is most commonly achieved through implementation of another Identity Manager product. The Identity Manager acts as both a Manager and Distributor by consolidating identity attributes, protecting those attributes at rest, and exposing a secure interface to push and/or pull those attributes to consumers through resource adapters and web services. 

The AAD can also be a separate product from the Manager. In this case, a physical or virtual directory can be the AAM, and a service layer may be built to serve as the Distributor and share identity attributes with consumers.

In order to ensure the security and integrity of the AAES, both users and consumer applications must interface with the service through a proxy or secure protocol following successful authentication. The AAD should be capable of exposing a wide range of secure communications protocols in order to meet the needs of the agency's consumer applications. The integration of each consumer application with the Distributor should be governed by an agreement that defines the specific attributes that will be provided and specifies data usage, distribution, and synchronization requirements. Although individual consumer applications may have access to different data, it is important for the AAES to have a common access management component to provide a consistent level of protection.


