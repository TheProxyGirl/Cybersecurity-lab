# Security Fundamentals

> Technical notes covering core cybersecurity principles, security objectives, identity and access management, security roles, and foundational security domains.

## 1. Core Security Concepts

### Cybersecurity
Cybersecurity is the practice of protecting systems, networks, applications, and data against unauthorised access, disruption, modification, and destruction.

### Threat
A potential cause of an unwanted security incident.

Examples:
- Malware
- Phishing
- Credential theft
- Insider threats

### Vulnerability
A weakness in a system, application, configuration, or process that could be exploited.

Examples:
- Unpatched software
- Excessive user permissions
- Misconfigured firewall rules

### Exploit
A technique or piece of code that takes advantage of a vulnerability.

### Risk
The possibility of loss or damage when a threat exploits a vulnerability, considering the likelihood and potential impact.

### Attack surface
The collection of points where a system, network, or application could be exposed to potential attacks.

### Security control
A safeguard designed to reduce risk or protect assets.

Examples:
- Multi-factor authentication (MFA)
- Firewalls
- Endpoint detection and response (EDR)
- Access controls
- Security monitoring

## 2. The CIA Triad

The CIA triad describes three fundamental objectives of information security.

| Principle | Definition | Example |
|---|---|---|
| Confidentiality | Preventing unauthorised access to information | Encryption and access controls |
| Integrity | Protecting information against unauthorised modification | Hash verification and change monitoring |
| Availability | Ensuring authorised users can access systems and information when needed | Backups, redundancy and DDoS protection |

### Security applications

- Confidentiality: sensitive information must only be accessible to authorised users.
- Integrity: unauthorised changes to files, records, or system configurations must be prevented or detected.
- Availability: systems and services must remain accessible and recoverable.

A single incident can affect multiple CIA objectives.

Example: ransomware may affect availability by making files inaccessible and integrity if files are modified.

## 3. Fundamental Security Principles

### Defence in Depth
Using multiple layers of security controls so that the failure of one control does not automatically compromise the entire system.

Example:
- Firewall
- Endpoint protection
- MFA
- Network segmentation
- Centralised logging

### Least Privilege
Users, applications, and services should receive only the permissions necessary to perform their intended tasks.

Example: a standard user account should not have unrestricted administrator privileges.

### Separation of Duties
Dividing sensitive responsibilities between multiple people or roles to reduce the risk of fraud, abuse, or unauthorised actions.

Example: one employee requests a payment, while another independently approves it.

### Security by Design
Security should be considered throughout the design and development of a system rather than added only after deployment.

Example: implementing access controls, secure defaults, and logging during application development.

### Keep It Simple (KISS)
Avoiding unnecessary complexity in systems, configurations, and security processes.

Example: reducing unnecessary services and removing unused firewall rules to simplify administration and reduce potential attack paths.

**Key principle:** Security controls should reduce risk while remaining understandable, maintainable, and appropriate to the environment.

## 4. Identity and Access Management (IAM)

Identity and Access Management (IAM) concerns how identities are managed and how access to resources is controlled.

### AAAA Framework

For these notes, AAAA stands for Administration, Authentication, Authorization, and Audit.

#### Administration
Creating, maintaining, modifying, and disabling identities and their associated access rights.

Example: creating a new employee account and removing access when an employee leaves.

#### Authentication
Verifying that an identity is genuine.

Examples:
- Passwords
- Multi-factor authentication
- Security keys
- Certificates

#### Authorization
Determining which resources and actions an authenticated identity is permitted to access.

Example: an employee can read a document but cannot modify or delete it.

#### Audit
Recording and reviewing relevant security events to establish what happened, when it happened, and which account or system was involved.

Examples:
- Login records
- Permission changes
- Privileged actions
- Failed authentication attempts

### Important distinctions

- Identification: claiming an identity.
- Authentication: proving control of the claimed identity.
- Authorization: determining permitted actions.
- Auditing: recording and reviewing activity.

Authentication does not automatically grant unrestricted access.

### Related concepts

**Principle of Least Privilege:** access should be limited to what is required.

**Role-Based Access Control (RBAC):** permissions are assigned to roles, and users receive permissions through their assigned roles.

**Multi-Factor Authentication (MFA):** authentication using two or more different factor types, such as something you know, something you have, or something you are.

**Privileged Access Management (PAM):** controls for managing and monitoring powerful accounts and permissions.

## 5. Security Roles and Responsibilities

### Security Operations Centre (SOC) Analyst
Monitors security events, investigates alerts, identifies suspicious activity, and escalates incidents.

Typical activities:
- Reviewing SIEM alerts
- Analysing authentication events
- Investigating suspicious IP addresses and processes
- Correlating events across multiple log sources

### Incident Responder
Investigates and manages security incidents to limit damage, understand what happened, and support recovery.

Typical activities:
- Triage and investigation
- Containment
- Evidence collection
- Recovery coordination
- Post-incident review

### Digital Forensics and Incident Response (DFIR) Analyst
Combines incident investigation with the collection and analysis of digital evidence.

Typical activities:
- Analysing endpoint and system artefacts
- Examining logs and timelines
- Investigating suspicious processes and files
- Reconstructing attacker activity
- Preserving evidence and documenting findings

### Security Engineer
Designs, implements, maintains, and improves security technologies and controls.

### Penetration Tester
Assesses systems for security weaknesses within an authorised scope and reports findings.

## 6. Foundational Security Tools

| Tool or category | Primary purpose |
|---|---|
| SIEM | Collecting and correlating security events from multiple sources |
| EDR | Monitoring endpoints and supporting detection, investigation, and response |
| Firewall | Controlling network traffic according to configured rules |
| IDS | Detecting potentially suspicious network or system activity |
| IPS | Detecting and potentially blocking suspicious activity inline |
| Wireshark | Capturing and analysing network packets |
| Linux command-line tools | Inspecting systems, processes, permissions, and network activity |
| Vulnerability scanner | Identifying known vulnerabilities and potential misconfigurations |

Tools provide evidence and capabilities; their output still requires interpretation and validation.

## 7. Foundational Security Domains

### 1. Security and Risk Management
Security governance, policies, risk assessment, compliance, and organisational security responsibilities.

### 2. Asset Security
Protecting information and assets through classification, ownership, handling, retention, and secure disposal.

### 3. Security Architecture and Engineering
Designing and implementing secure systems, infrastructure, and technical controls.

### 4. Communication and Network Security
Protecting network infrastructure and data in transit through segmentation, secure protocols, traffic controls, and monitoring.

### 5. Identity and Access Management (IAM)
Managing identities, authentication, authorization, and access privileges.

### 6. Security Assessment and Testing
Evaluating security controls through testing, vulnerability assessments, audits, and other authorised assessment activities.

### 7. Security Operations
Monitoring systems, investigating suspicious activity, responding to incidents, and maintaining security controls.

**Note:** These are seven broad introductory study areas, not an exhaustive or universally standardised list of cybersecurity domains.

## 8. Practical Security Reasoning

When investigating a potential security issue, consider the following questions:

1. What asset or system is involved?
2. What activity was observed?
3. Which security objective may be affected: confidentiality, integrity, or availability?
4. Is there a relevant threat, vulnerability, or misconfiguration?
5. What evidence supports the hypothesis?
6. Which logs, tools, or additional data could help validate it?
7. What is the potential impact?
8. What action is appropriate, and does it require escalation?

**Example: Suspicious login activity**

Observation: several failed login attempts followed by a successful login from an unusual location.

Investigation:
- Review authentication logs and timestamps.
- Identify the affected account and source IP.
- Check MFA events and other account activity.
- Correlate the event with endpoint and network telemetry where available.
- Assess whether the activity is legitimate or potentially malicious.
- Escalate and follow the incident response process if warranted.

A suspicious indicator is a reason to investigate, not proof of compromise by itself.

## 9. Key Takeaways

- Cybersecurity reduces risks to systems, networks, and information.
- The CIA triad defines confidentiality, integrity, and availability.
- Defence in depth uses multiple security layers.
- Least privilege limits unnecessary permissions.
- Separation of duties reduces the risk of misuse.
- Security by design integrates security throughout a system's lifecycle.
- IAM manages identities and controls access.
- Security tools generate evidence that must be interpreted in context.
- Security operations depend on monitoring, investigation, and evidence-based decisions.

## 10. Learning Progress

- [x] Security fundamentals studied
- [x] CIA triad
- [x] Fundamental security principles
- [x] Introductory IAM concepts
- [x] Security roles and tools
- [x] Foundational security domains
- [ ] Practical security investigations
- [ ] Network traffic analysis
- [ ] Log correlation and incident investigation

**Current learning focus:** Network Traffic Understanding

**Next milestone:** Understand network addressing, routing, transport protocols, and how to interpret basic network traffic.
