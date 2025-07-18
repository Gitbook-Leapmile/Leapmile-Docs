# Supplier Assessment Questionnaire

**Query 1**: Provider undergoes regular third-party application security audits and is willing to share the results (applicable Standards: ISO 27001, SSAE 16, SOC 2).

**Response**: Currently, we are not ISO 27001 certified. However, we maintain an internal application security audit process that ensures a secure platform. Also, we are willing to conduct any special third-party security assessments and penetration testing to ensure the integrity and security of our systems, subject to being reimbursed for those additional expenses. We remain committed to maintaining a robust security posture and are actively working towards formal certification in the near future.

**Query 2**: MFA and/or single sign-on must be available as part of the standard service offering.

**Response**: Our products offer 2FA authentication via SMS one-time-use codes. These can be periodically invalidated as per required policy.

{% embed url="https://docs.leapmile.com/home/training-guides/multi-factor-authentication" %}

**Query 3:**

"Password management must be configurable to allow settings to comply with DPDHL Standards:

1. Personnel must be allowed to select and change their own passwords
2. If an account is password protected, it must be created with unique passwords. Such accounts must not have blank or zero-length passwords.
3. Temporary, new, or reset passwords must be unique to an individual
4. The process of entering a password must not be automated by using scripts (except for robotic accounts), programming keys, or auto-completion functions, unless using authorized tools (e.g., password manager).
5. A password reset procedure must be in place, during which the account owner’s authenticity is determined without any doubt through technology or corresponding staff ID confirmations. Password resets must be logged.
6. The system must prevent the user from using the previous passwords.
7. Accounts must be locked after the number of consecutive failed login attempts as defined.
8. If technically feasible, password change must be enforced by the system for all account types. The password change can be automatically enforced by the system or manually through procedural and organizational means
9. Password complexity and change frequency are determined based on account type and function (see the ""Password policy"" tab).
10. A complex password is defined as one made of three of the following four character types:\
    a. Uppercase letters,\
    b. Lowercase letters,\
    c. Numbers,\
    d. Special characters.
11. Password composition rules—the following must be avoided when a new password is created:\
    a. Dictionary words and common passwords (e.g., "Welcome1"), except a sequence of dictionary words composing a passphrase,\
    b. Family names, months, days, or any other aspect of the date (e.g., "Summer2021"),\
    c. User-ID, user name, user group, or other system identifier\
    d. Repeating characters, sequences, or any obvious combination (e.g., “DHL,” “password,” “123,” or “qwert”).

**Response**: Our products offer 2FA authentication via SMS one-time-use codes. These can be periodically invalidated as per required policy. asdasdas.

**Query 4**: Service can only be assessed via encrypted protocols. No legacy/breached protocols must be allowed.

**Response**: Our products offer 2FA authentication via SMS one-time-use codes. These can be periodically invalidated as per required policy.

{% embed url="https://docs.leapmile.com/home/engineering-and-design/secure-protocols" %}

**Query 5**:

Any user activity is logged, and logged information is available to DSC admins:

1. Login success
2. Logout success
3. Login failure
4. User activity

**Response**: Login information is logged and can be audited in logs if requested.

{% embed url="https://docs.leapmile.com/home/training-guides/password-logging" %}

**Query 6**:

Any admin activity is logged, and logged information is available to DSC admins.

1. Login success
2. Logout success
3. Login failure
4. Application configuration changes

**Response**: Login information is logged and can be audited in logs if requested.

{% embed url="https://docs.leapmile.com/home/training-guides/password-logging" %}

**Query 7**:

Any critical system activity is logged, and logged information is available to DSC Admins.

1. Warnings
2. Disruptions

**Response**: Logs can be provided upon request by authorized admin.

{% embed url="https://docs.leapmile.com/home/training-guides/system-monitor-and-alerts" %}

**Query 8**: The provider raises alerts to DSC in case of suspicious activities in the system.

**Response**: Relevant activities will be notified by mail to the DSC mail ID.

**Query 9**: Significant information security-related events and incidents must be communicated to DSC. Any external/internal cyberattack is treated as a security incident and reported without undue delay.

**Response**: We can notify authorized admins if there is any external or internal suspected cyberattack event.

{% embed url="https://docs.leapmile.com/home/engineering-and-design/security-incident-notification-process" %}

**Query 10**: A vulnerability management process covering all layers of the solution (e.g., OS, DB, middleware, application) must be in place, allowing immediate response to critical vulnerabilities.

**Response**: We have not hired an external PEN service to certify our systems but have designed them with the appropriate safeguards in place.

{% embed url="https://docs.leapmile.com/home/engineering-and-design/vulnerability-and-patch-management-process" %}

**Query 11**: Provider can guarantee that data will be only stored and processed within the EEA or countries with an EU adequacy decision. If not feasible, the provider must offer equal safeguards.

**Response**: While data generated in India is stored in an Indian data center, we ensure that all processing activities adhere to strict data protection standards that are equivalent to those outlined under the GDPR.

Technical and Organizational Measures (TOMs): Encryption at rest and in transit, role-based access control, and data minimization and anonymization where appropriate.

Local Compliance: All data handling practices are designed to comply with the Indian Digital Personal Data Protection Act (DPDPA) and related regulations, ensuring local legal compliance.

Access and Oversight: Access to data is restricted to authorized personnel, and we maintain logs of data access and processing activities.

Incident Response and Notification: A documented incident response plan is in place, and in case of a data breach, timely notifications are issued.

**Query 12**: Supplier administrators must not have access to customer data unless explicitly granted for incident resolution.

**Response**: Our systems will not access or store any DHL customer data. All data we receive will be obfuscated or be indirect IDs, so there should not be any risk.

{% embed url="https://docs.leapmile.com/home/engineering-and-design/rto-and-rpo-goals" %}

**Query 13**: Provider ensures recovery of services after a major disrupting incident (e.g., natural hazard or cyberattack) as agreed in the contract by executing regular backup restore tests.

**Response**: Our databases are fault tolerant with replicas and periodic backups in place.

**Query 14**: All information entered into the service is owned by DSC and can only be used by DSC. The provider must provide a means to extract all DSC-entered information.

**Response**: Will implement as requested.

**Query 15**: A privacy policy is adopted at the board/top management level that ensures compliance with all applicable regulatory requirements related to the processing and protection of personal data.

**Response**: Available on our website already.

**Query 16**: The provider should have a privacy/data protection officer in place who is responsible for the privacy/data protection program, policy, and assessments throughout the organization.

**Response**: These contact details can be provided.

{% embed url="https://docs.leapmile.com/home/engineering-and-design/privacy-and-data-protection-statement" %}

**Query 17**: The provider should have a procedure in place to support their clients in meeting their statutory obligations in relation to data subject requests received under privacy and data protection laws.

**Response**: There is no current process document for this workflow. We will respond to any request in an expeditious manner.

{% embed url="https://docs.leapmile.com/home/engineering-and-design/privacy-and-data-protection-statement" %}

**Query 18**: The provider should have a standardized process of regularly conducting privacy or data protection impact assessments and managing any risks identified.

**Response**: There is no current process document for this workflow. We will respond to any request in an expeditious manner.

{% embed url="https://docs.leapmile.com/home/engineering-and-design/privacy-and-data-protection-statement" %}

**Query 19**: The provider should maintain a data breach response plan that complies with the duty to notify clients, regulatory authorities, and data subjects in inline with regulatory requirements.

**Response**: There is no current process document for this workflow. We will respond to any request in an expeditious manner.

{% embed url="https://docs.leapmile.com/home/engineering-and-design/security-incident-notification-process" %}
