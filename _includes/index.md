# Streamling Collection and Sharing of Digital Identity Data
----------------------------------------------------------------

**What is the Streamline Identity Management Playbook?**

Your agency collects the digital identity data of employees, contractors, and individuals who have access to resources that support your agency’s core business operations. This data is used in many processes, including the issuance of credentials and management of access to your agency’s physical and logical resources. Digital identity data must be managed reliably to ensure that access control decisions across your agency are based on accurate and current information.

This playbook will give you the answers to several common digital identity questions, including:

> * How do I determine which identity attributes are needed to identify a person within my agency?
  
> * How do I discover or locate authoritative data sources for particular identity data attributes in my agency?
  
> * How are authoritative data sources designated and protected?

> * What approaches exist to help my agency manage digital identities more effectively?

<br>

**How is the playbook structured?**

We developed this playbook into 4 high-level topic areas and 10 individual steps, or activities. Within each step, you will find a checklist to help you perform that activity and additional guidance, like implementation tips or security and privacy considerations.

<br>

**How was the playbook developed?**

This playbook was created using updated and migrated content that previously was found in the FICAM Roadmap and Implementation Guidance v2.0. We hope that the new format encourages you and your agency to contribute to additional content to support the management of digital identities across the Federal government.

<br>

**Where can I find additional content?**

The FICAM Architecture provides a high-level overview of identity management and a description of the services that deliver identity management capabilities. We recommend that you visit the FICAM Architecture site to gain a basic understanding of identity management and how its role in broader federal Identity, Credential, and Access Management (ICAM)

<br>

**How can I contribute to this playbook?**

We look forward to your use and contribution to this playbook. Please visit our contribute page to learn how to post questions and contribute content.

------------------------------------------------------------------------------------------------------------------------------------------------------

### <center> Table of Contents </center>


**[Plan Your Digital Identity Collection and Sharing Process](#plan)**
	
> * [Step 1:](#step1) Determine which Core Identity Attributes your agency will collect
  
> * [Step 2:](#step2) Identify which system(s) will serve as the Authoritative Data Source(s)

<br>

**[Integrate Digital Identity Management Processes](#integrate)**

> * [Step 3:](#step3) Enhance and Improve back-end collection processes

> * [Step 4:](#step4) Streamline HR Processing

> * [Step 5:](#step5) Streamline Background Investigation Processing

> * [Step 6:](#step6) Streamline Contractor Processing

<br>

**[Design Your Authoritative Attribute Exchange Service (AAES)](#design)**

> * [Step 7:](#step7) Address the protocol, payload, and policy of your attribute exchange

> * [Step 8:](#step8) Establish a process(es) to link identity attributes

> * [Step 9:](#step9) Integrate your AAES with your existing IT infrastructure

> * [Step 10:](#step10) Implement attribute management and distribution functionality

<br>

**[Final Implementation Considerations](#considerations)** 

<br>

-------------------------------------------------------------------------

# <span style="color: #0C5C89"><a name="plan"></a>Plan Your Digital Identity Collection and Sharing Process</span>

Your agency should move towards developing an enterprise digital identity for its users. This identity is a single digital representation of an individual’s identity, maintained at an enterprise level, which uses attributes from authoritative source systems. This differs from many agency environments, where agencies often rely on locally-managed user identity accounts comprised of redundantly-collected identity attributes. The following steps provide guidance on the initial setup and planning of the collection process.


## <span style="color: #a61406"><a name="step1"></a>**Step 1: Determine which Core Identity Attributes your agency will collect**</span>

An agency typically collects a wide variety of data elements about its employees, contractors, and other support staff who have access to agency resources. Within this data set, smaller subsets of attributes enable an agency to uniquely identify an individual within the organization and support the execution of meaningful access control decisions. This data set is known as the core digital identity. 

The ICAM Subcommittee developed the government-wide Core Person Model for agencies working to align with the FICAM Architecture, which will assist in the management and sharing of digital identity records.  As shown in the table below, the Core Person Model provides a common definition for the attributes that contain a digital identity record within the Federal Government. 

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

### Checklist


> * **Map agency data to the model.** After you’ve identified the location of each data element, you should map the data model to the Core Person Model to tailor it for agency use. 

> * **Determine additional core data elements, if necessary.** If  more attributes are necessary to support the implementation of the Core Person Model, they should be limited to the elements needed to uniquely identify an individual within the organization and that support your agency’s specific mission needs. Other identity attributes may be collected to support enhanced access control scenarios, but these are considered entitlement attributes, not part of the basic digital identity record. 

> * **Identify opportunities for process integration.** You should identify redundancies in data collection associated with the Core Person Model and determine opportunities to integrate and streamline these business processes by referencing existing identity data. 


### Benefits

> * **Eliminate redundant identity data creation.** Your agency will be able to reduce or eliminate the need for extra business processes that may collect redundant identity data for specific application use. 

> * **Enable interoperability and more robust identity attribute sharing.** Your agency is provided a common basis for sharing identity attributes internally. When combined with the establishment of attribute management and distribution services, agencies are able to offer enhanced attribute sharing capabilities for use by programs and applications across the organization. 

> * **Streamline identity life cycle management.** The administrative burden associated with identity life cycle management will be greatly reduced, while improving data quality and accuracy. 

> * **Increase the accuracy and reliability of provisioned identities.** This will provide consistency across enterprise identities and improve the accuracy of user account data established through automated provisioning workflows.


## <span style="color: #a61406"><a name="step2"></a>**Step 2: Identify which system(s) will serve as the Authoritative Data Source(s)**</span>

An authoritative data source for identity is a repository or system that contains attributes about an individual and is considered to be the primary or most reliable source for this information. In the case that two or more systems have mismatched or have conflicting data, the data within the authoritative data source is considered the most accurate.

Within many federal agencies, authoritative identity data is dispersed across a number of different systems that are often independently managed. Some agencies, however, may operate a single centralized repository of identity data, such as an Identity Management System (IDMS). While your agency is not required to have a single repository of identity data, it’s expected your agency designate an authoritative data source for each data element in the Core Person Model and work to minimize the number of data sources used to collect and maintain the same identity information. In cases where an agency houses identity data elements across several authoritative data sources, it’s recommended that it share or map identifiers between the data sources to avoid collisions and errors.


### Checklist 

> * **Determine where identity data is stored.** Identifying which systems/resources are authoritative for specific identity attributes involves determining where identity attributes are first recorded and updated. 

> * **Perform an analysis to identify which of those source systems should be designated as authoritative.** To comply with HSPD-12, many agencies have already identified authoritative data sources for the data elements that are required as part of the PIV enrollment and issuance process. It’s likely, however, that your agency will need to conduct added authoritative source discovery to identify an authoritative source for each data element contained in the Core Person Model.

> * **Document and map digital identity data elements.** Mapping should be done based on how the data is originated, types of transformations that occur to the data, and where the data is stored. It’s possible for one system to be authoritative for data element creation and a second system to be authoritative for data element modification. For example, an employee’s initial building and room number may be created in the PACS, whereas subsequent changes to building and room may be handled in an employee locator system. It’s still important to ensure that there is only one authoritative source for data creation and only one for data modification.

The table below provides a number of common characteristics that you should look for as part of the discover process:

<br>

| <center> Characteristic </center>        | <center> Description </center> |
|------------------------------------------|--------------------------|
| **Primary Source** | Where an identity data element originates. The data is not received from another system or resource. |
| **Legal Authority to Collect** | Generally operates with a legal authority to collect certain data elements as part of the organization's mission (e.g., HR has the legal authority to collect identity data within federal agencies). |
| **Data Accuracy** | Considered to be accurate and reliable for a specific attribute(s) at any given time. |
| **Data Freshness** | Contains the most up-to-date data available and is generally the first system to be updated when data changes. |
| **Data Accessibility** | Limits the availability of certain data elements to those individuals or groups that have a need to know. |
| **Data Protection** | Has restrictions in place that limit the ability to change stored data to a select group of users. |
| **Data Ownership** | Generally owned and maintained by groups that own the data itself and can vouch for its authenticity. |
| **Data Modification** | Performs modification of data originated elsewhere (e.g., updating identity attributes for use in downstream processes, data normalization) and becomes authoritative by virtue of performing the modification. |

<br>

> * **Prepare Authoritative Data Source.** Data preparation and cleanup is needed to remove redundancies and discrepancies in the data housed within authoritative data sources. If your agency has multiple authoritative sources, it should evaluate the merits of consolidating data sources where appropriate. As identity data from authoritative data sources is shared with downstream processes, further data preparation requirements will evolve (e.g., ensuring employment status information can be read by both logical access control systems (LACS) and physical access control systems (PACS) to trigger de-provisioning workflows).

> * **Perform real-time or periodic synchronization.** Synchronization should occur in the authoritative data source as well as areas where the data is shared to ensure that identity data is current. For example, if the data attribute for an employee’s bureau/component affiliation changes in the authoritative data source, the change should be synchronized in other systems that use this data element. This is an important step in cases where identity attributes are used to determine access privileges on a resource.

> * **Ideally, only modify Core identity data in one place.** Applications and processes reliant on authoritative data shouldn’t have the capability to manipulate authoritative data. Instead, they should only consume data and make business decisions based on them. Your agency should determine the logical place for updating each data attribute based upon the business processes that typically initiate the change (e.g., an agency personnel security system is a logical place for updates to background investigation status data).

> * **Define processes that ensure the most accurate and recent identity data resides in the authoritative source.** There may be cases in which a downstream application has more recent data than the data housed in the authoritative source. In such cases, your agency should be capable of processing and approving out-of-band change requests to ensure the data in the authoritative data source is appropriately updated.

<br>

### Security and Privacy Considerations

Authoritative data sources are subject to the security and privacy requirements in accordance with the Federal Information Security Management Act (FISMA) of 2002 and the Privacy Act of 1974. Given the sensitive nature of the information contained within authoritative identity data sources, your agency should closely observe the requirements outlined in FISMA and consider implementing optional enhancements to provide an additional measure of security, if justified based on the information system risk classification. Potential enhancements include:

> * **Enforcement of strict access permissions.** To maximize data integrity within authoritative data sources, agencies should take steps to ensure that the information contained within authoritative data sources cannot be manipulated or changed without strict rules and enforcement mechanisms.

> * **Appropriateness of data usage.** Agencies should take additional measures beyond the FISMA requirements to ensure that data usage or exchange stemming from authoritative data sources can be recorded and audited to ensure that data is accessed, used, and shared in accordance with security and privacy policies.

> * **Employee security enhancements.** Agencies should consider applying the security enhancements associated with high-impact systems, outlined in SP-800-53, to authoritative data sources. Doing so requires that additional security controls are put in place to protect the system and its data.

> * **Verify authoritative source authenticity.** It may be desirable for downstream applications that rely on identity data from authoritative sources to validate the attributes provided by the source. This typically includes verifying the identity of the source and the time at which it validated the attribute values. This can be accomplished by verifying a digital signature placed by the authoritative source around selected groups of attribute- value pairs or by a real-time verification service.

> * **Provide redress capability.** In accordance with the Privacy Act of 1974, your agency should ensure that users have redress capabilities to rectify errors associated with identity records. This capability improves the accuracy and freshness of authoritative data, while also providing a level of transparency for end-users and consumers of identity data.

<br>

| <center> Case Study </center> |
|-------------------------------|
| Sometimes identifying an authoritative source can lead to other efficiencies. Treasury identified HRConnect as its authoritative source of core identity data for employees and contractors. As a result, Treasury was able to establish HRConnect as the originator of the Treasury Unique Identifier (TrUID), which is used to link users in USAccess, Treasury Enterprise Director, and bureau Identity Management Systems (IDMS) through the user’s lifecycle. As a result, data quality is dramatically improved, while reducing redundant data collection. |

<br>

| <center> Implementation Tip #1 </center> |
|------------------------------------------|
| Many agencies maintain an inventory of systems and applications that house Personally Identifiable Information (PII), often referenced in Systems of Record Notices (SORNs). This inventory can provide a starting point for determining which agency systems can serve as authoritative data sources for identity attributes. As a SORN specifies the permissible, or routine, use of the data in a particular system of records, modification will be necessary if the information will be used in a different way than anticipated. |

<br>

| <center> Implementation Tip #2 </center> |
|------------------------------------------|
| Partially automating requests for redress within the standard IT environment can help speed up the processing time and improve data quality. However, requests for redress should never be processed without human review, because of the risk of falsification of identity details. |

<br>

---------------------------------------------------------------------
<br>

# <span style="color: #0C5C89"><a name="integrate"></a>Integrate Digital Identity Management Processes</span>

Agencies collect identity data through a number of disparate processes that are conducted by offices and groups throughout the organization. These include new hire on-boarding, background investigation processing, credentialing, and access control administration. Typically, each of these processes is a manual, separate, and often redundant point for obtaining identity data.

Your agency should seek to streamline and integrate digital identity management processes and minimize the number of collection points for identity data, while reducing or eliminating the use of paper-based forms as identity data collection methods. These improvements are expected to help agencies achieve greater process efficiency and improve the security and privacy around the collection and maintenance of digital identity data.

<br>

## <span style="color: #a61406"><a name="step3"></a>**Step 3: Enhance and Improve back-end collection processes**</span>

Back-end processes are used to obtain identity data to determine where processes can be enhanced and improved. Per OMB Circular A-123, management is responsible for establishing and maintaining internal controls to achieve the objectives of effective and efficient operations, reliable financial reporting, and compliance with applicable laws and regulations. This responsibility is also held by ICAM implementers, who are accountable for improving the effectiveness, quality, and productivity of federal programs and operations. The goals of OMB Circular A-123 closely align with the effort to improve the processes within an agency that collect identity data.

<br>

### Checklist

> * **Conduct internal information gathering with business owners to identify all of the processes within the core business areas that involve collection of identity.** Use specific criteria to define what constitutes a core business process. Take steps to ensure successful engagement and participation of relevant process owners. Take steps to ensure the availability of process and related data element information gathered.

> * **Examine these processes and document the collection methods and types of identity information that is collected.** Identity inefficiencies. Determine which process steps provide value and which do not. Take note of process frequency. Inventory the data sources. Understand how long both the entire process and each step/section takes. Perform quality checks to determine accuracy and completeness of information.

> * **Use information from the data analysis to identify and prioritize improvement opportunities for inclusion in an implementation plan.** Isolate redundancies in process steps, forms, and data elements. Identify paper-based collection methods that can be automated. Identify manual data entry points.

> * **Provide implementation plan to business process owners and provide recommendations on how to streamline, automate, and enhance identity data collection.** Integrate similar, redundant processes. Minimize duplicative information collection. Replace paper-based collection processes with electronic methods, as appropriate. Automate manual processes, as appropriate.

> * **Business process owners put the implementation plan into action.** Implement relevant metrics for digital identity processes. Establish training needs. Make updates to relevant process documentation, etc.

> * **Develop methods for continuously monitoring and measuring success of the process improvement effort.** Conduct surveys to trach end-user satisfaction. Conduct surveys to support staff productivity and satisfaction. Capture process efficiency, data quality, and cost savings. Establish governance and reporting requirements. Create a process control board. Review audit logs and workflow of sensitive information flows.

<br>

### Benefits

> * **Increased levels of process efficiency.** The need to manually collect and manage data significantly decreases, allowing agencies to focus on core business functions.

> * **Cost savings.** Reducing the number of hours spent collecting, managing, and reconciling identity data, along with fewer required systems and processes to store and maintain data, will lead to lower costs.

> * **Enhanced security and privacy.** Integrating digital identity creation processes results in fewer collection points, reducing opportunities for data leakage and/or theft through automated access control to identity data. Furthermore, eliminating paper-based collection methods also reduces additional security and space requirements associated with storing and securing paper files.

> * **Enhanced compliance with Federal regulations and guidance.** The tight integration of the digital identity creation processes and elimination of paper-based collection methods helps agencies comply with the Government Paperwork Elimination Act (GPEA).

<br>

| <center> Privacy Tip </center> |
|--------------------------------|
| Electronic security methods (e.g., encryption, role-based access control, etc.), when deployed as part of an agency’s overall security program, can be more efficient, more reliable, and less expensive than traditional methods (e.g., locked rooms, filing cabinets, etc.) for protecting sensitive data. However, an agency should consult with its Privacy Offer to ensure these electronic methods adhere to privacy laws, directives, and policies. |

<br>

## <span style="color: #a61406"><a name="step4"></a>**Step 4: Streamline HR Processing**</span>

The Human Resources (HR) department is usually the primary source of personal data for federal employees and support staff within many agencies. HR is usually the first group within an agency to receive an individual’s identity information, often through the job application and employee on-boarding processes. By targeting integration and streamlining of these HR processes, you can see significant benefits to user life cycle management.

<br>

### Checklist

> * **Streamline data exchange.** Integrate agency recruiting systems with government-wide applications to enable pre-population of on-boarding data provided by the applicant during the recruiting process.

> * **Digitize the on-boarding process.** Allow employees to complete and track the progress of HR on-boarding forms online.

> * **Integrate various HR systems.** Systems used by your agency’s HR department and the bureau/component level may operate separately to perform the same business processes, such as recruiting and on-boarding. These systems should be consolidated to eliminate redundant data collection and management.

> * **Use digital signatures.** The use of digital signatures may allow your agency to more easily detect forgery or tampering by verifying that a form was created by a known person.

> * **Establish an employee self-service portal.** Set up an online capability that allows employees to securely update their data, such as address, emergency contacts, and direct deposit account information. These data changes would ideally be populated downstream to reliant systems.

<br>

## <span style="color: #a61406"><a name="step5"></a>**Step 5: Streamline Background Investigation Processing**</span>

Data collected during a background investigation contains a person’s core digital identity. By integrating and streamlining personnel security and background investigation processes, the processes around creating and populating the digital identity can be significantly improved.

<br>

### Checklist

> * **Use data captured during the PIV enrollment process.** Capturing data once and reusing it creates a more efficient process, while a limited number of data collection points enhances data privacy. For example, many biographic data elements (e.g., name, DOB) collected during PIV enrollment can also be used during the background investigation to reduce redundancy.

> * **Integrate background investigation processing into other processes.** The number of steps necessary to initiate a background investigation can be reduced by integrating this process with other existing business processes. For example, instead of manually tracking the due dates for reinvestigations, consider building a system that automatically tracks reinvestigation dates and prompts the personnel security specialist to initiate reinvestigations at the appropriate time.

> * **Leverage authoritative sources of identity information.** Agencies should use their internal authoritative sources of identity data (e.g., HR systems) and share this information with the systems and applications that are used to track and conduct investigations (e.g., OPM‘s e-QIP). Doing so can minimize the amount of identity data that must be manually re-entered during the background investigation process.

> * **Eliminate paper-based investigative forms.** Aim to eliminate the use of paper forms and manual processes to support investigation processing through OPM. Agencies should also use automated electronic processing solutions, such as OPM‘s electronic Agency Delivery of investigative results.

> * **Honor reciprocity for investigations performed by other agencies.** Previous guidance has identified the lack of reciprocity in accepting background investigations completed by or on behalf of another agency as a key gap in performing background investigations. Agencies should use the capabilities provided within the Central Verification System (CVS) to report and view the adjudication results of background investigations.

<br>

### CVS Database

The Office of Personnel Management (OPM) is responsible for maintaining the CVS database. The CVS stores information related to security clearance, suitability, and access decisions for contractor personnel. OPM also stores data related to credentialing determinations under HSPD-12, suitability or fitness for federal employment, fitness for contractor employees, and eligibility for access to classified information to facilitate reciprocity.

Your agency’s responsibilities relating to the use of the CVS include the following:

> * Report all adjudicative decisions on background investigations to OPM.

> * Supply bulk records and HSPD-12 information to CVS via transaction files through the OPM Secure Portal, or through individual entries through the Personnel Investigations Processing System (PIPS) Agency Menu.

> * Make daily updates to the information in the CVS to report any changes, such as adding new clearances, noting revocations, denials, suspensions, and administratively withdrawn clearances. Agencies are required to fully refresh their CVS clearance data at least monthly.

> * Consult the CVS to determine if an existing investigation is sufficient to meet your agency’s need before initiating a new background investigation request. 

> * Create processes to ensure the accuracy and maintenance of the information provided to the CVS. OPM does not own this information and other agencies may rely on it to make credentialing decisions.

> * Ensure the appropriate data elements are entered into the CVS for each applicable record (e.g., name, DOB, investigation, clearance level, status, etc.).

<br>

## <span style="color: #a61406"><a name="step6"></a>**Step 6: Streamline Contractor Processing**</span>

Although contractors may require similar access to federal employees, the methods and locations for collecting and maintaining their identity data are often very different. Digital identities for the contractor population can be challenging to manage due to a number of factors, including:

> * Managing identity data for contractors has not been required to support contracting business functions, unless required based on the nature of the contract.

> * Contractor information is often obtained through a variety of different processes and managed separately for individual resources when it’s collected to support access.

> * Many agencies don’t have existing authoritative sources for contractor identity data.

> * The contractor population is fluid, as individuals often change the projects, bureau/component, or agencies they are affiliated with.

To overcome these challenges, your agency should establish a process for managing contractor identity data for contractors who require identity credentials and access to agency resources.

<br>

### Checklist

> * **Enhance on-boarding process.** Your agency should replace manual, paper-based forms and processes with digital methods (e.g., digital signatures, online portals) wherever possible during the contractor on-boarding process. This process should be communicated and followed by all relevant parties so there’s no ambiguity in the way contractors are introduced into the agency.

> * **Minimize collection points.** Within the streamlined on-boarding process, your agency should minimize the points at which contractor data is collected. If possible, there should be one step in the on-boarding process where contractors provide their identity data, such as the background investigation process. A single collection point will help eliminate redundancy, increase efficiency, and ease management of contractor information.

> * **Identity gaps in contractor data.** After deciding where contractor information will be collected, your agency should compare the data elements to the Core Person Model and identify discrepancies. It’s beneficial for your agency to have consistent attributes across all groups within their population, so your agency should ensure they collect similar information from contractors when creating their digital identity.

> * **Create a single authoritative source.** Usually, agencies don’t have a single authoritative source for contractors, which can make management of their data challenging. Your agency should establish an authoritative source for contractors by either creating a separate repository or tying it into an existing system that holds employee data (e.g., IDMS).

> * **Analyze options for data retention.** Since contractors normally begin and end many different contracts while working with an agency, agencies should analyze their options for retaining contractor data after the contract ends. Your agency should determine a length of time for maintaining contractor data in their systems that is cost-effective and compliant with the Fair Information Privacy Principle of data minimization.

> * **Improve account and status change processes.** Your agency should establish a process for making changes to contractor information that uses current workflows and business processes. Agencies could also consider implementing a self-service portal that allows authorized individuals to make changes to their identity information and status. This option could improve data integrity and reduce the burden on the agency‘s support staff.

> * **Enhance off-boarding process.** Your agency should establish a streamlined process for managing contractor identity records as they end their work with the agency. This process should be communicated to and followed by all relevant parties so there’s no ambiguity in the way contractors are released from the agency. The responsibility for completing the off-boarding process should be assigned to a specific person (e.g., sponsor) or office (e.g., personnel security).

> * **Ensure PIV card collection.** Contractors’ PIV cards must be collected during the off-boarding process. Not collecting a PIV card can have a number of negative impacts on the agency including security risks, inaccurate information on the status of their contractor population, and unnecessary costs for the management of their PIV card ($3 per month per card for the GSA Managed Service Office).

> * **Include Contract requirement.** A requirement should be incorporated into contracts requiring that all government property, including PIV cards, be returned when the contract is completed.

> * **Develop policies.** Your agency should establish a policy that details the approach for collecting and managing contractor identity data and communicate this policy across the agency and include it in all contracts

<br>

-------------------------------------------------------------------------------
<br>

# <span style="color: #0C5C89"><a name="design"></a>Design your Authoritative Attribute Exchange Service (AAES)</span>

Agencies have a common need to collect and share basic identity data within their organization to support credential issuance, provisioning of user accounts, and access control administration. The Authoritative Attribute Exchange Service (AAES) capability is the means to share authoritative identity attributes within an agency securely. An AAES is a technical solution that gives agencies the ability to connect various authoritative data sources and share identity and other attributes with the shared enterprise infrastructure.

The AAES capability will allow your agency to link the authoritative sources of identity information with customers of identity data across the agency, eliminating the need to redundantly collect identity data at each point where it’s used.

## <span style="color: #a61406"><a name="step7"></a>**Step 7: Address the protocol, payload, and policy of your attribute exchange**</span>

When seeking to electronically share attribute data between authoritative source systems and relying parties, you must be address protocols, payload, and agency policies to support the attribute exchange.

> * **Identity a common exchange protocol.** This allows the involved parties to communicate using the same language and set of rules. Your agency should select a protocol that meets the technical needs of both the Identity Provider and Relying Party when establishing an attribute sharing capability. The selection of a protocol that meets your agency’s need also depends on the type of connection that is preferred between the parties. You should also be aware that different types of connections might not be equally supported by all approved protocols.

The table below describes several common protocols used for exchanging identity data.

<br>

| <center> Protocol </center> | <center> Description </center> |
|:---------------------------:|------------------------------------------|
| **LDAP/s** | Lightweight Directory Access Protocol is used to read and/or edit directories. Traffic to and from the directory should be encrypted (i.e., TLS, SSL, Internet Protocol Security). Access control should be in place to ensure data is provided to only those authorized to view it. |
| **DSML** | Directory Service Markup Language provides directory service information in an XML syntax. Data traverses across HTTP/s. |
| **SAML**| Security Assertion Markup Language is used to exchange authentication and authorization data in XML. |
| **SPML**| Service Provisioning Markup Language is an open standard that uses an XML-based framework for the integration and interoperation of service provisioning requests. |

<br>

> * **Define which attributes will be exchanged and how they will be formatted.** Defining attribute syntax (e.g., format) helps ensure that identity attributes are received in such a manner that they are usable within a relying party application. This is typically accomplished by establishing an attribute contract (Definition - A document that extensively describes the agreement on the set of, and syntax of, attributes that members of a federation have to abide by on the payload.) When streamlining the exchange and management of identity data within an agency, it’s expected that the payload will align with the government-wide Core Person Model. However, an agency may opt to include additional attributes based on its specific mission and business needs.

> * **Establish an exchange policy.** Establishing governance is important to maintain the ongoing operation of identity attribute sharing arrangements and to provide a framework ensuring both the Identity Provider and Relying Party(s) operate within the boundaries of the arrangement. An agency implementing an internally-focused attribute sharing capability should establish agency policies governing the appropriate use of identity data that is made available through the solution. This can often lessen the need for point-to-point agreements between groups within the organization.

<br>

| <center> Privacy Tip </center> |
|--------------------------------|
| Implementing an attribute sharing capability provides an agency with a number of benefits and process efficiencies. However, one goal of this effort is to avoid collecting and/or sharing more Personally Identifiable Information (PII) than is necessary for the intended use. Therefore, only collect the attributes necessary to share with a relying party. To achieve this, agencies should consider establishing attribute agreements or attribute practice statements to address which attributes will be shared and the manner in which they will be conveyed, to ensure privacy and security. |

<br>

## <span style="color: #a61406"><a name="step8"></a>**Step 8: Establish a process(es) to link identity attributes**</span>

Agencies should eliminate duplicate and/or redundant digital identity records to ensure that each federal user has only a single digital identity. Managing a single digital identity record for each user within the organization requires that an agency establish a process to link or bind identity attributes to the appropriate record. There are three common techniques for accomplishing this: (1) Unique Person Identifiers, (2) Multi-Attribute Keys, and (3) Manual Identity Attribute Correlation. 

<br>

### Checklist

> * **Evaluate approaches for linking identity attributes to the appropriate record and determine which method meets your needs.**

>> **Approach #1: Unique Person Identifiers.** 

>> A unique person identifier is an alphanumeric string attribute that identifies a person’s enterprise digital identity from others, even in cases where the underlying identity attributes may be the same (e.g., two employees with the same name). If your agency chooses to implement a single enterprise system for managing identity data, unique person identifiers should be used to correlate identity data in advance of the implementation to ensure the system is populated with accurate data. Despite any changes to an individual‘s role within the organization (e.g., a contractor becomes a federal employee), these identifiers are generally assigned to an individual as part of the initial on-boarding process and persist throughout the digital identity life cycle. Agencies aren’t required to establish unique person identifiers. However, doing so can help streamline the processes required to manage digital identity and support the implementation of other ICAM programs.

>> Unique person identifiers are best used when:

>>> * Performing direct access lookups of digital identities

>>> * Reconciling collisions between identity attributes that occur as a result of automated matching processes

>>> * Limiting data discrepancies when binding identity data to an individual across multiple agency systems

<br>

| <center> Benefit </center> | <center> Description </center> |
|-------------------------------------------------------------|
| **Reduced data discrepancies** | Correlate identity data for the same individual across multiple systems. Using a unique person identifier helps to easily detect and resolve conflicts between different sources of identity attribute data and helps to ensure the uniqueness of an identity across the enterprise. |
| **Streamlined digital identity creation** | Streamline the process for reconciling attributes into a single digital identity by eliminating the need to manually correlate attributes across various source systems. |
| **Modernized access control** | Using a unique person identifier provides an agency with a greater degree of confidence when granting user access in an automated fashion because the identity attributes that are used to support authentication and authorization decisions are bound to an individual‘s digital identity through the unique identifier. |
| **Streamlined federated identity management** | In a federated environment, agencies can correlate identity data by sharing their unique person identifiers, called parallel person identifiers. Alternatively, an agency can add an agency-specific code to its unique person identifier or have its own agency-specific code added to another organization‘s unique person identifier. Doing so would extend the attribute‘s uniqueness and reciprocity across the broader Federal Government community. |
| **Visibility into identity data** | Agencies will better understand the user‘s role and entitlements across the enterprise. This data can be analyzed within an agency or between agencies for account auditing, threat identification, privilege correlation, and compliance. |

<br>

>> **Approach #2: Multi-Attribute Keys**

>> A multi-attribute key is a combination of identity attributes that can be bound to serve as an identifier for user records across multiple systems. A multi-attribute key is a combination of identity attributes that can be bound to serve as an identifier for user records across multiple systems. This approach allows your agency to take advantage of data that is already available to the agency and would likely require less modification to existing systems. Additionally, multi-attribute keys provide a layer of redundancy, which can help address an error in a single attribute that is part of the key. If an error is present, an agency can analyze the other identity attributes within the key to determine the correct individual. This may be desirable to some agencies to mitigate the risks associated with poor data quality.

<br>

>> **Approach #3: Manual Identity Attribute Correlation**

>> In cases where unique person identifiers or multi-attribute keys aren’t used, it’s likely that your agency will need to apply additional processes to bind identity attributes for an individual. This type of attribute correlation is often labor and time intensive. In addition, use of manual attribute correlation can reduce the ability to detect and resolve security and audit issues that may arise in identity records and user accounts (e.g., duplicate entries for the same individual due to status or affiliation changes). This can also result in duplicate user accounts and identity records appearing in other agency applications. Duplicate user accounts can drive up software licensing costs on some applications, and the accounts may not be detected and terminated when a user leaves the agency.

>> Despite these challenges, your agency might choose this approach, because there is only a minimal need to change business processes and upgrade or procure technology. This might also serve as a transitional approach until regular technology refresh cycles allow an agency to implement a more automated solution to achieve greater levels of efficiency.

<br>

> * **Align the method with existing or planned capabilities.**

>> **Approach #1: Unique Person Identifiers**

>> When implementing a system to create and manage unique person identifiers, your agency should ensure that these attributes are randomly generated in a way the identifier cannot be easily guessed by a third party. Identifiers should be generated according to a common standard, algorithm, or naming convention. The identifier itself shouldn’t be based on commonly available information about the individual, and such information about the user shouldn’t be able to be obtained by manipulation or reverse engineering.

>> Unique identifiers shouldn’t be derived from or linked to data that is subject to change, such as user biographic data or credential-specific numbers. For example, the Federal Agency Smart Credential Number (FASC-N) or optional Universally Unique Identifier (UUID) of the PIV card shouldn’t be used as a person’s enterprise unique identifier if the intended use is to link the identity record to the user‘s active credential. These numbers are linked to a specific credential and change with each consecutive card issued to that person. If your agency is only seeking an authoritative originator for its unique numbers and the identifier can persist across the user’s digital identity life cycle, a card identifier may be a viable option. As an alternative, an agency should establish a separate unique person identifier attribute (i.e., not linked to a credential) that is intended to support digital identity management for managed identities that will span multiple credentials.

>> Although there may be multiple authoritative sources containing different sets of data about an individual, the unique identifier should be generated from one originator. Doing so eliminates the possibility of collision or conflict between identifiers issued from different sources. In some cases, it may make sense for your agency to generate a unique identifier with an existing system that houses digital identity data (e.g., HR or PIV card enrollment). Some of these systems, however, only contain identity data for a portion of the total user population and should be extended to include the entire intended user population if they will be used to create unique identifiers.

>> It’s also important that unique identifiers be reconciled on a regular basis to ensure there’s neither redundant identifiers nor the same identities with different identifiers. If fraudulent enrollment is a concern, your agency can leverage one-to-many biometric matching against the entire enrolled community to detect duplicate enrollments and reconcile individuals who may have more than one identifier.

>> Your agency should consider the life cycle of unique person identifiers and establish a policy to govern if identifiers for identities that are no longer valid can be recycled and reused. Your agency‘s policy for the life cycle of unique person identifiers should seek to address the following:

>>> * **Identifier Longevity.** Your agency should set a life span (years) that must expire before an identifier could be recycled, which should be at least as long as the potential life span of any archived records associated with the user.
>>> * **Management of identifiers.** Your agency should determine how identifiers will be managed for a user that has become inactive, but may reinitiate his/her affiliation with the agency in the future. Doing so ensures that an identifier is not made available for re-use during the defined life span.
>>> * **Temporary users.** Your agency should determine if temporary users not expected to return in the future will obtain unique identifiers from the same system/process as other users, or if a secondary namespace with lower longevity is needed.

<br>

>> **Approach #2: Multi-Attribute Keys**

>> To establish a multi-attribute key, your agency must designate an attribute set (two or more identity attributes) to serve as key fields within its relational database system(s). Your agency should choose attributes which, when combined, are sufficient to tell the difference among users within their agency community. For example, combining name, date of birth (DOB), entrance on duty date, and home telephone number is likely to be enough to tell the difference between individuals that might share a common attribute (e.g., the same name). Once a multi-attribute key has been established, the database system will then enforce this property as new records are added across the database. When duplicate identifiers are compared, these key fields will be analyzed to further refine the search and identify the correct record.

>> When selecting attributes to form a multi-attribute key, your agency should evaluate the use of attributes that are considered PII. PII is generally subject to use restrictions, which could affect the availability of a multi-attribute key that includes a PII data element.

<br>

>> **Approach #3: Manual Identity Attribute Correlation**

>> Correlating identity attributes can typically be accomplished in two ways:

>>> * Develop a correlation algorithm that must be manually applied by an administrator through a batch process; or

>>> * Manual linking by an administrator using a pre-defined rule set

>> Within your agency or organization, each application may have different naming standards for user account creation. Without a unique identifier or multi-attribute key to serve as the primary key, it may be necessary to develop unique correlation algorithms for every application in the enterprise. In addition to requiring additional development time, this process may also introduce additional risk in successfully identifying related records during correlation activities. To resolve these errors, administrators would then spend additional time manually verifying identities, attributes, and entitlements and reconciling each account within the application.

<br>

| <center> Implementation Tip #1 </center> | 
|------------------------------------------|
| Request for Comments (RFC) 4122, A Universally Unique Identifier (UUID) Uniform Resource Namespace, offers agencies a standardized approach for creating unique person identifiers using time-based, name-based, or random number algorithms. Leveraging an approach like RFC 4122 is the preferred approach to creating identifiers, as it results in an infinitesimally small chance of collision, without the need for a managed identifier namespace. |

<br>

| <center> Implementation Tip #2 </center> |
|------------------------------------------|
| Treasury’s HRConnect has been identified as the authoritative source of core identity data for employees and contractors within Treasury. As a result, HRConnect is the originator of the Treasury Unique Identifier (TrUID), which is used to link users in USAccess, Treasury Enterprise Directory, and bureau Identity Management Systems (IDMS) through the user’s lifecycle. This approach dramatically improves data quality and reduces redundant collection of data. | 

<br>

| <center> Lessons Learned </center> | 
|------------------------------------|
| A federal agency with a large user base began a logical access control system (LACS) modernization effort, initially relying on manual attribute correlation techniques to bind identity attributes to digital identities. Early in the implementation, the agency determined that the time and effort associated with manually resolving data collisions had significant impacts to the cost and schedule of the overall effort. To mitigate this, the agency implemented a unique person identifier system, which offered a more efficient approach to identity correlation. | 

<br>

## <span style="color: #a61406"><a name="step9"></a>**Step 9: Integrate your AAES with your existing IT infrastructure**</span>

Designing an AAES solution architecture requires agencies to consider the capabilities presented in the FICAM Architecture, existing ICAM investments (e.g., logical access solutions), and your agency’s overall IT infrastructure. The goal of this step is to find how an AAES capability will integrate with your agency’s IT infrastructure and provide digital identity attribute sharing services.

An AAES provides a consolidated system for securely and electronically exchanging digital identity attributes between authoritative data sources and your agency applications that consume those attributes. In many cases, this data is spread across multiple authoritative sources within your agency, which complicates the challenge of exchanging attributes between sources and consumers. The AAES should be primarily comprised of two specific solution components:

> * Authoritative Attribute Manager. Provides the capability to present a single, authoritative view of that data by reconciling and aggregating attributes from the various sources.

> * Authoritative Distributor. The component that integrates with attribute consumers and conducts the data exchange.

The FICAM Architecture [Applications View](http://gsa.github.io/ficam-arch/applications/) provides a view of general enterprise ICAM applications and systems. It represents multiple solutions that your agency may choose to use. The solution components are represented generically and could be implemented using a variety of Commercial Off-The-Shelf (COTS) or purpose-built products. Your agency should evaluate its existing ICAM and infrastructure investments and select the approach that best meets their needs.

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

<br>

## <span style="color: #a61406"><a name="step10"></a>**Step 10: Implement attribute management and distribution functionality**</span>

This step describes the functionality and approaches for implementing the AAES Infrastructure components, the Authoritative Attribute Manager (AAM) and the Authoritative Attribute Distributor (AAD). In some cases, it may be possible to achieve the functionality described for both the AAM and AAD by implementing a single product or tool. On the other hand, it’s also possible that multiple products and/or purpose-built applications could be integrated to create a single AAES solution. Your agency should evaluate their existing and planned ICAM investments as well as the agency’s infrastructure and select an implementation approach that best meets the business needs and mission requirements of your agency.

<br>

### Checklist

> * **Analyze which AAM implementation option meets your needs.** The Authoritative Attribute Manager (AAM) compares identity attributes from different authoritative data sources within an agency and provides a single authoritative source of digital identity. It acts as a central hub of attributes by combining data from the various sources through either resource connectors or web services. As a result, the attribute manager de-conflicts differences that exist in the same attribute between multiple sources. The AAM can be implemented in several ways, based on an agency’s existing investments and infrastructure requirements, including:

>> * **Virtual Directory.** Combines and normalizes identity attributes, without the need to store them in a physical location, while also synchronizing attributes with authoritative data sources. When requested, the virtual directory searches the authoritative data sources and provides normalized attributes to the attribute consumer.

>> * **Metadirectory.** Similar to a virtual directory, in that it combines and normalizes identity attributes from multiple authoritative sources. However, it also involves physically storing the results of the data aggregation and synchronizing with the authoritative data stores in regular intervals.

>> * **Identity Manager.** The Identity Manager component of a modernized logical access control system (LACS) is capable of providing the identity attribute aggregation and normalization capabilities of the AAM. Agencies choosing to use an Identity Manager as part of their LACS modernization effort should prefer this approach to avoid redundant investment in this capability.

<br>

| <center> Approach </center> | <center> Benefits </center> | <center> Limitations </center> |
|-------------------------------------------------------------------------|
| **Virtual Directory** | •	Attributes are queried in real-time and results are dynamically provided to relying parties <br><br> • No requirement to physically store identity data eliminates privacy concerns associated with systems of record <br><br> • Ability to develop custom views for each relying party ensures that identity data is not shared inappropriately <br><br> • Ability to easily support a large number of authoritative data sources <br> • Data provided to consumer applications is always up-to-date with authoritative sources | • Dynamic querying places an additional performance load on authoritative source systems, but can be addressed through data caching <br><br> • Some authoritative data sources for identity data may not be built to support dynamic querying <br><br> • Pushing authoritative identity data to consumer applications requires an additional tool (Authoritative Attribute Distributor) <br><br> • AAES and consumer systems may be unable to pull data when the authoritative source is unavailable, but can be addressed through data caching |
| **Metadirectory** | • Minimal impact to performance authoritative data sources <br><br> • Queries by relying parties can be responded to faster due to local storage of data <br><br> • Minimally invasive to source systems that may have more complicates or proprietary data stores | • Data is physically stored locally, which is redundant with authoritative data sources and creates a new system of record <br><br> • Local data storage requires that appropriate security and privacy controls are in place <br><br> • May not be up-to-date with authoritative sources given synchronization schedule <br><br> • Pushing authoritative identity data to consumer applications requires an additional tool (Authoritative Attribute Distributor) |
| **Identity Manager** | • Opportunity to leverage an existing LACS investment <br><br> • Natively provides an ability to push identity data to consumers without the need for an additional component <br><br> • Streamlined integration with access control components <br><br> • Provides a number of enhanced capabilities, including provisioning, workflows to augment/enhance attributes, and user self-service | • Requires that agencies procure an Identity Manager (if one is not already owned) <br><br> • Some Identity Manager products may require that attributes be stored in a physical directory after aggregation |

<br>

> * **Establish your Authoritative Attribute Distributor.** The AAM itself is not directly accessed by systems or people that request attributes; rather it collaborates with the Authoritative Attribute Distributor (AAD). The AAD serves as the interface point for requesting applications. This provides an additional layer of security that prevents requesting parties from directly accessing the attributes, which could potentially lead to unauthorized disclosure. <br> <br>The AAD is designed to integrate with the AAM to provide attributes to consumer applications (i.e., applications that use identity data for downstream processes), both inside and outside the agency. The AMM can also be used to synchronize user data with user accounts or local directories, based on your agency’s requirements. The AAD serves as the primary communication point for consumer applications in that it both receives and responds to requests for attributes by pulling the appropriate attributes from the AAM. This capability provides applications with streamlined access to the attributes they requested while protecting the AAM (and its connected authoritative sources) from direct access from users and consumer applications, reducing the complexity of protecting the security and privacy of the data. <br><br> The AAD component can be the same product as the AAM. This is most commonly achieved through implementation of another Identity Manager product. The Identity Manager acts as both a Manager and Distributor by consolidating identity attributes, protecting those attributes at rest, and exposing a secure interface to push and/or pull those attributes to consumers through resource adapters and web services. The AAD can also be a separate product from the AAM. In this case, a physical or virtual directory can be the AAM, and a service layer may be built to serve as the Distributor and share identity attributes with consumers. <br><br> To ensure the security and integrity of the AAES, both users and consumer applications must interface with the service through a proxy or secure protocol following successful authentication. The AAD should be capable of exposing a wide range of secure communications protocols in order to meet the needs of your agency’s consumer applications. The integration of each consumer application with the Distributor should be governed by an agreement that defines the specific attributes that will be provided and specifies data usage, distribution, and synchronization requirements. Although individual consumer applications may have access to different data, it’s important for the AAES to have a common access management component to provide a consistent level of protection.

> * **Implement the Authoritative Attribute Manager (AAM).** While it would be ideal to define a single authoritative source for each identity attribute in the Core Person Model, it may not always be possible. For example, your agency may need to combine data from different HR systems for a single person. It may be necessary to refine the data to ensure the various attributes are formatted in a way they can be used by the applications and users that receive authoritative data through the AAES. The Attribute Manager is also capable of extending the schema for an identity, if there’s a need for additional attributes that aren’t included in the implementation of the Core Person Model. <br><br> By combining and comparing identity data in the Attribute Manager, attributes can be found in one location, improving consistency of data, as there is a single authoritative source. The Attribute Manager also provides your agency with the chance to support a number of enhanced capabilities, including support for multiple access control models at the application level that operate based on a variety of digital identity data elements. This capability allows agencies to make more secure, accurate, and reliable access control decisions and enforce access controls on a more detailed level.

| <center> Lessons Learned </center> |
|------------------------------------|
| Treasury’s PIV Data Synchronization solution includes a Data Management Service (DMS) that compares identity data from multiple authoritative sources and provides synchronization with relying systems. By making up-to-date identity data easily available to relying party systems, the DMS reduces redundant data collection and improves data accuracy throughout the agency. |

<br>

| <center> Privacy Tip </center> |
|--------------------------------|
| When determining an appropriate approach to implementing an AAM, an agency should work with its Privacy Office to determine whether there is an existing Systems of Record Notice (SORN) in place or if a new SORN needs to be developed. The agency should also determine if a Privacy Impact Assessment (PIA) is required. If a new or updated PIA and/or SORN are necessary, then they must be in place before the approach can be developed and implemented. |

<br>

--------------------------------------------------------------------------------
<br>

# <span style="color: #0C5C89"><a name="considerations"></a>Final Implementation Considerations</span>

Deploying an AAES capability requires considerable planning, support, and coordination from various groups with your agency. Specific planning and coordination considerations include the following:

> * **Data Quality.** Identity data needs to be stored in a consistent and defined format prior to implementing the AAM and must be up-to-date. If the quality of data is poor going into the AAES, then the data shared from the AAES will also be poor quality.

> * **Defining Identities.** If there are multiple sources of identity attributes, the AAM should be able to determine which source is authoritative and should be used to define the digital identity.

> * **Flexible Authoritative Attribute Source Selection.** Many agencies don’t have a central location to create, update, and store all attributes used throughout the agency. Therefore, if there are conflicting values from different sources for the same attribute, it’s important to develop a process for identifying and selecting the most accurate value. These processes may range from identifying which record was most recently updated to comparing multiple sources and selecting the value which appears most often.

> * **Correlation of Identity Attributes.** Given the number of potential sources for identity attributes, your agency should determine a mechanism for correlating those attributes into a single digital identity within the Attribute Manager. That is, each person needs to be uniquely identified and attributes of the same identity from different sources should be linked to the same digital identity. Attributes can be linked using a unique person identifier or a combination of attributes (i.e., a multi-attribute key). If a reliable correlation key doesn’t exist, a mechanism must be developed for accurately linking identity information, perhaps involving a federal employee’s review of potentially conflicting records.

> * **Normalization.** Normalization creates a common and consistent classification for attributes. It provides a mapping between different attribute types and values. For example, one bureau/component’s organization attribute can be equivalent to another’s division attribute. Establishing a process for normalizing these attributes (e.g., data modeling) across your agency is critical to enabling effective attribute sharing.

> * **Reconciliation of Identity Attributes.** While correlating attributes to an identity, different authoritative sources may have different or missing data regarding the same identity attribute. A process needs to be put in place to correct the differences and store the correct attribute in the AAM. This often requires manual review of the attributes. The problem also needs to be fixed upstream, which can be achieved by creating a data scanning tool to check for error conditions before populating the AAM. Another option would be to build a process to notify the appropriate personnel to correct the source data manually.

> * **Sensitivity of Data.** Due to the sensitivity of identity data, it’s extremely important to ensure that proper access controls are in place. The various tools used to implement an AAES can provide enhanced security and privacy for an individual’s PII. For example, specific views can be created based on a user’s role to limit access to sensitive data elements. This can be a good method to satisfy users with different reporting requirements while protecting sensitive data from those who lack a need to know it.

> * **Securing the AAES.** Access controls alone aren’t enough protection. Other security processes should be put in place to protect the AAES, including:

>> * Ensuring traffic travels through firewalls to filer application and network layer attacks

>> * Protecting data with encryption while at rest and during transit

>> * Using a logging tool that will allow for periodic security audits

>> * Using monitoring tools to ensure the integrity of the AAES hasn’t been compromised

> * **Access to the AAES.** The requesting party should never have direct access to the attributes contained within the AAM component of the AAES. It’s expected that the majority of attribute consumers will be other agency IT applications that will obtain attributes from the AAD based on a defined attribute agreement or MOU. This is recommended because it makes it harder attackers to access the Attribute Manager by not knowing the true address of the Attribute Manager.

> * **Access Control Groups.** To streamline the process of interfacing with the AAES, attributes can be grouped based on sensitivity (e.g., public, confidential, confidential PII) or business level roles (e.g., HR, benefits administration, access control administration, etc.). Groups of attributes can then be requested based on the need and usage criteria.

> * **Integration into System Development Life Cycle (SDLC).** Your agency should consider adding a step into its SDLC to ensure that new applications consider how to integrate with and use the AAES. This may involve providing a standard method for requesting applications to provide justification, get approved, and sign a governance agreement for receiving the data. It may also involve establishing a process for quickly creating new access control groups and/or attribute views as they are requested.

> * **Push vs. Pull.** Pulling data refers to consumers requesting data using the AAD’s service layer. Pushing data refers to the AAD sending data back to authoritative sources and downstream applications. Both pushing and pulling of data should be accounted for during implementation to accommodate the varying capabilities of legacy systems that will consume the attributes.

> * **Use of Attribute Service for More than Identity.** While the scope of this section has focused on identity attributes, a similar architecture (or the same AAES) can be used or expanded upon to include entitlement attributes.

> * **Governance of Attribute Sharing.** Agencies should consider establishing guidelines to protect against unauthorized disclosure of identity information. This include establishing an attribute agreement or MOU to define which attributes will be made available to specific attribute consumers via the AAES. Taking this step ensures that attribute consumers are provided with the information necessary to effectively make authorization decisions while limiting the exposure of unnecessary information.










































