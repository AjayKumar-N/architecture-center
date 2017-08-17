﻿# Implement Strong Access Control Measures

## PCI DSS Requirement 6: Restrict access to cardholder data by business need to know  

To ensure critical data can only be accessed by authorized personnel, systems and processes must be in place to limit access based on need to know and according to job responsibilities.
“Need to know” is when access rights are granted to only the least amount of data and privileges needed to perform a job.

> **Note:** These requirements are defined by the [Payment Card Industry (PCI) Security Standards Council](https://www.pcisecuritystandards.org/pci_security/) as part of the [PCI Data Security Standard (DSS) Version 3.2](https://www.pcisecuritystandards.org/document_library?category=pcidss&document=pci_dss). Please refer to the PCI DSS for information on testing procedures and guidance for each requirement.

### PCI DSS Requirement 6.1

**6.1** Establish a process to identify security vulnerabilities, using reputable outside sources for security vulnerability information, and assign a risk ranking (for example, as “high,” “medium,” or “low”) to newly discovered security vulnerabilities.

> **Note:** Risk rankings should be based on industry best practices as well as consideration of potential impact. For example, criteria for ranking vulnerabilities may include consideration of the CVSS base score, and/or the classification by the vendor, and/or type of systems affected. 
> 
> Methods for evaluating vulnerabilities and assigning risk ratings will vary based on an organization’s environment and risk-assessment strategy. Risk rankings should, at a minimum, identify all vulnerabilities considered to be a “high risk” to the environment. In addition to the risk ranking, vulnerabilities may be considered “critical” if they pose an imminent threat to the environment, impact critical systems, and/or would result in a potential compromise if not addressed. Examples of critical systems may include security systems, public-facing devices and systems, databases, and other systems that store, process, or transmit cardholder data.

**Responsibilities: `Shared`**

|||
|---|---|
| **Microsoft&nbsp;Azure** | Procedures have been established and implemented to scan for vulnerabilities on hypervisor hosts in the scope boundary. Vulnerability scanning is performed on server operating systems, databases, and network devices with the appropriate vulnerability scanning tools. The vulnerability scans are performed on a quarterly basis at minimum. Microsoft Azure contracts with independent assessors to perform penetration testing of the Microsoft Azure boundary. Red-Team exercises are also routinely performed and results used to make security improvements. |
| **Customer&nbsp;PCI<br />Blueprint&nbsp;(PaaS)** | The Contoso Webstore reduces the risk of security vulnerabilities using an Application Gateway with WAF, and the OWASP ruleset enabled. For more information, see [PCI Guidance - Mitigation of the Risk of Security Vulnerabilities](reference.md#mitigation-of-the-risk-of-security-vulnerabilities).|



### PCI DSS Requirement 6.2

**6.2** Ensure that all system components and software are protected from known vulnerabilities by installing applicable vendor-supplied security patches. Install critical security patches within one month of release.

> **Note:** Critical security patches should be identified according to the risk ranking process defined in Requirement 6.1.

**Responsibilities: `Shared`**

|||
|---|---|
| **Microsoft&nbsp;Azure** | Microsoft Azure is responsible for ensuring all network devices and hypervisor OS software is protected from known vulnerabilities by installing applicable vendor-supplied security patches. Unless a customer requests to not use the service, a patch management process exists to ensure that operating system level vulnerabilities are prevented and remediated in a timely manner. Production servers are scanned to validate patch compliance on a monthly basis. |
| **Customer&nbsp;PCI<br />Blueprint&nbsp;(PaaS)** | The Contoso Webstore is a PaaS service solution. Azure provides maintenance of all service patches.|



### PCI DSS Requirement 6.3

**6.3** Develop internal and external software applications (including web-based administrative access to applications) securely, as follows:
- In accordance with PCI DSS (for example, secure authentication and logging)
- Based on industry standards and/or best practices
- Incorporating information security throughout the software-development life cycle 

> **Note:** This applies to all software developed internally as well as bespoke or custom software developed by a third party.

**Responsibilities: `Shared`**

|||
|---|---|
| **Microsoft&nbsp;Azure** | Microsoft Azure applications and endpoints are developed in accordance with the Microsoft Security Development Lifecycle (SDL) methodology which is in line with DSS requirements. |
| **Customer&nbsp;PCI<br />Blueprint&nbsp;(PaaS)** | The Contoso Webstore was designed to follow industry best practices for protecting CHD. Deployment guidance provides the details of the security meassures, and logging is enabled.|



### PCI DSS Requirement 6.3.1

**6.3.1** Remove development, test and/or custom application accounts, user IDs, and passwords before applications become active or are released to customers.

**Responsibilities: `Shared`**

|||
|---|---|
| **Microsoft&nbsp;Azure** | A Final Security Review (FSR) is performed for major releases prior to production deployment by a designated Security Advisor outside of the Azure development team to ensure only applications ready for production are released. As part of this final review it is ensured that all test accounts and test data have been removed. |
| **Customer&nbsp;PCI<br />Blueprint&nbsp;(PaaS)** | The Contoso Webstore provides a staging service that is logged and isolated. Each of the network tiers has a dedicated network security group [NSG]. For more information, see [PCI Guidance - Network Security Groups](reference.md#network-security-groups).|



### PCI DSS Requirement 6.3.2

**6.3.2** Review custom code prior to release to production or customers in order to identify any potential coding vulnerability (using either manual or automated processes) to include at least the following:
- Code changes are reviewed by individuals other than the originating code author, and by individuals knowledgeable about code-review techniques and secure coding practices.
- Code reviews ensure code is developed according to secure coding guidelines
- Appropriate corrections are implemented prior to release
- Code-review results are reviewed and approved by management prior to release 

> **Note:** This requirement for code reviews applies to all custom code (both internal and public-facing), as part of the system development life cycle. 
>
> Code reviews can be conducted by knowledgeable internal personnel or third parties. Public-facing web applications are also subject to additional controls, to address ongoing threats and vulnerabilities after implementation, as defined at PCI DSS Requirement 6.6.

**Responsibilities: `Shared`**

|||
|---|---|
| **Microsoft&nbsp;Azure** | Microsoft Azure applications and endpoints are developed in accordance with the Microsoft Security Development Lifecycle (SDL) methodology. |
| **Customer&nbsp;PCI<br />Blueprint&nbsp;(PaaS)** | The Contoso Webstore provides a staging service that is logged and isolated. Each of the network tiers has a dedicated network security group [NSG]. For more information, see [PCI Guidance - Network Security Groups](reference.md#network-security-groups).|



### PCI DSS Requirement 6.4

**6.4** Follow change control processes and procedures for all changes to system components. The processes must include the following (see Requirements 6.4.1 to 6.4.6):

**Responsibilities: `Shared`**

|||
|---|---|
| **Microsoft&nbsp;Azure** | Microsoft follows NIST guidance regarding security considerations in software development in that information security must be integrated into the SDLC from system inception. Continual integration of security practices in the Microsoft SDL enables:<ul>
| **Customer&nbsp;PCI<br />Blueprint&nbsp;(PaaS)** | The Contoso Webstore demo provides a staging service that is logged and isolated. 



### PCI DSS Requirement 6.4.1

**6.4.1** Separate development/test environments from production environments, and enforce the separation with access controls.

**Responsibilities: `Shared`**

|||
|---|---|
| **Microsoft&nbsp;Azure** | See "Microsoft Azure" section for [Requirement 6.4](#pci-dss-requirement-6-4). |
| **Customer&nbsp;PCI<br />Blueprint&nbsp;(PaaS)** | The Contoso Webstore provides a staging service that is logged and isolated. Each of the network tiers has a dedicated network security group [NSG]. For more information, see [PCI Guidance - Network Security Groups](reference.md#network-security-groups).|



### PCI DSS Requirement 6.4.2

**6.4.2** Separation of duties between development/test and production environments

**Responsibilities: `Shared`**

|||
|---|---|
| **Microsoft&nbsp;Azure** | See "Microsoft Azure" section for [Requirement 6.4](#pci-dss-requirement-6-4). |
| **Customer&nbsp;PCI<br />Blueprint&nbsp;(PaaS)** | The Contoso Webstore provides a staging service that is logged and isolated. Each of the network tiers has a dedicated network security group [NSG]. For more information, see [PCI Guidance - Network Security Groups](reference.md#network-security-groups).|



### PCI DSS Requirement 6.4.3

**6.4.3** Production data (live PANs) are not used for testing or development

**Responsibilities: `Shared`**

|||
|---|---|
| **Microsoft&nbsp;Azure** | See "Microsoft Azure" section for [Requirement 6.4](#pci-dss-requirement-6-4). |
| **Customer&nbsp;PCI<br />Blueprint&nbsp;(PaaS)** | The Contoso Webstore has no live PAN data.|



### PCI DSS Requirement 6.4.4

**6.4.4** Removal of test data and accounts from system components before the system becomes active / goes into production.

**Responsibilities: `Shared`**

|||
|---|---|
| **Microsoft&nbsp;Azure** | See "Microsoft Azure" section for [Requirement 6.4](#pci-dss-requirement-6-4). |
| **Customer&nbsp;PCI<br />Blueprint&nbsp;(PaaS)** | The Contoso Webstore does not have any test accounts.|



### PCI DSS Requirement 6.4.5

**6.4.5** Change control procedures for the implementation of security patches and software modifications must include the following:
- **6.5.4.1** Documentation of impact.
- **6.5.4.2** Documented change approval by authorized parties.
- **6.5.4.3** Functionality testing to verify that the change does not adversely impact the security of the system.
- **6.5.4.4** Back-out procedures.

**Responsibilities: `Shared`**

|||
|---|---|
| **Microsoft&nbsp;Azure** | See "Microsoft Azure" section for [Requirement 6.4](#pci-dss-requirement-6-4). |
| **Customer&nbsp;PCI<br />Blueprint&nbsp;(PaaS)** | The Contoso Webstore is a PaaS service solution. And Azure provides maintenance of all service patches.|



### PCI DSS Requirement 6.4.6

**6.4.6** Upon completion of a significant change, all relevant PCI DSS requirements must be implemented on all new or changed systems and networks, and documentation updated as applicable.

> **Note:** This requirement is a best practice until January 31, 2018, after which it becomes a requirement.


**Responsibilities: `Shared`**

|||
|---|---|
| **Microsoft&nbsp;Azure** | See "Microsoft Azure" section for [Requirement 6.4](#pci-dss-requirement-6-4). |
| **Customer&nbsp;PCI<br />Blueprint&nbsp;(PaaS)** | The Contoso Webstore is a PaaS service solution. And Azure provides maintenance of all service patches.|



### PCI DSS Requirement 6.5

**6.5** Address common coding vulnerabilities in software-development processes as follows:
- Train developers in secure coding techniques, including how to avoid common coding vulnerabilities, and understanding how sensitive data is handled in memory.
- Develop applications based on secure coding guidelines.

> **Note:** The vulnerabilities listed at 6.5.1 through 6.5.10 were current with industry best practices when this version of PCI DSS was published. However, as industry best practices for vulnerability management are updated (for example, the OWASP Guide, SANS CWE Top 25, CERT Secure Coding, etc.), the current best practices must be used for these requirements 

> **Note:** Requirements 6.5.1 through 6.5.6, below, apply to all applications (internal or external). Requirements 6.5.7 through 6.5.10, below, apply to web applications and application interfaces (internal or external) 

- **6.5.1** Injection flaws, particularly SQL injection. Also consider OS Command Injection, LDAP and XPath injection flaws as well as other injection flaws.
- **6.5.2** Buffer overflows
- **6.5.3** Insecure cryptographic storage
- **6.5.4** Insecure communications
- **6.5.5** Improper error handling
- **6.5.6** All “high risk” vulnerabilities identified in the vulnerability identification process (as defined in PCI DSS Requirement 6.1).
- **6.5.7** Cross-site scripting (XSS)
- **6.5.8** Improper access control (such as insecure direct object references, failure to restrict URL access, directory traversal, and failure to restrict user access to functions).
- **6.5.9** Cross-site request forgery (CSRF)
- **6.5.10** Broken authentication and session management

**Responsibilities: `Shared`**

|||
|---|---|
| **Microsoft&nbsp;Azure** | See "Microsoft Azure" section for [Requirement 6.4](#pci-dss-requirement-6-4). |
| **Customer&nbsp;PCI<br />Blueprint&nbsp;(PaaS)** | Contoso Webstore demo provides guidance to secure development,  a DFD and threat model to illustrate secure development practices.|



### PCI DSS Requirement 6.6

**6.6** For public-facing web applications, address new threats and vulnerabilities on an ongoing basis and ensure these applications are protected against known attacks by either of the following methods:
- Reviewing public-facing web applications via manual or automated application vulnerability security assessment tools or methods, at least annually and after any changes 
> **Note:** This assessment is not the same as the vulnerability scans performed for Requirement 11.2. 
- Installing an automated technical solution that detects and prevents web-based attacks (for example, a web-application firewall) in front of public-facing web applications, to continually check all traffic.

**Responsibilities: `Shared`**

|||
|---|---|
| **Microsoft&nbsp;Azure** | Microsoft Azure tests public-facing web applications as part of its SDL process before applications are deployed to the production environment. Additionally, Microsoft scans all public-facing web applications in production on a regular basis to detect any possible vulnerabilities. |
| **Customer&nbsp;PCI<br />Blueprint&nbsp;(PaaS)** | The reference solution reduces the risk of security vulnerabilities using an Application Gateway with WAF, and the OWASP ruleset enabled. For more information, see [PCI Guidance - Mitigation of the Risk of Security Vulnerabilities](reference.md#mitigation-of-the-risk-of-security-vulnerabilities).|



### PCI DSS Requirement 6.7

**6.7** Ensure that security policies and operational procedures for developing and maintaining secure systems and applications are documented, in use, and known to all affected parties.

**Responsibilities: `Customer Only`**

|||
|---|---|
| **Microsoft&nbsp;Azure** | Not applicable. |
| **Customer&nbsp;PCI<br />Blueprint&nbsp;(PaaS)** | The reference solution reduces the risk of security vulnerabilities using an Application Gateway with WAF, and the OWASP ruleset enabled. For more information, see [PCI Guidance - Mitigation of the Risk of Security Vulnerabilities](reference.md#mitigation-of-the-risk-of-security-vulnerabilities).|



