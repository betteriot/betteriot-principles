# IoT Mark Principles
(Manually synced mirror of GDoc; to comment, [file an issue](https://github.com/openiotmark/iotmark-principles/issues))
 
Open IoT Certification Mark Principles – March 9th 2018

This work by iotmark.org is licensed under Creative Commons BY-SA 4.0.

This is the latest version of a working document to develop a certification mark for connected products by community members worldwide. This is a work in progress and you may comment freely, join the conversation on Slack, sign up to our newsletter or give us feedback in writing (alex@iot.london) or on our monthly open calls. 

This is a set of principles that we think an organisation—a connected product manufacturer, team or founder—would use to make a good, secure, ethical, product that also takes into account the upcoming General Data Protection Regulation (GDPR) directive. But also to push beyond the GDPR and look at the entire life cycle of a smart device. From manufacture, to final disposal.

The terminology in this document is a bit technical, bear with us. We use MUST, SHOULD, and MAY because of a technical writing standard called RFC 2119. 

## Privacy

### 1. The device the organisation supplies MUST be GDPR compliant. 

Assessment criteria: GDPR policy is published on the organisation website / a simple checklist is completed. Use our checklist. 

### 2. The organisation MUST NOT sell customer data without consent.

Assessment criteria: TODO

### 3. Their customer data MUST NOT be used for profiling, marketing or advertising without transparent disclosure.

Assessment criteria: ICA complaint (registration number)

## Interoperability

### 4. The organisation MUST allow third parties to connect clients to its backend.

Assessment: TODO

### 5. The organisation MAY allow third parties to connect devices to its backend. 

Assessment criteria: The organisation provides URL(s) of publicly accessible documentation of the backend Application Programming Interface (API) for all of the following aspects:
- Endpoints (e.g. api.example.com)
- API (e.g. GET /things, e.g. described with Swagger)
- Protocol (e.g. HTTP, MQTT, ...)
- Data format (e.g. JSON, XML; clearly defined data types)
- Data model / information model (e.g. service topics, how to measure temperature)

### 6. The organisation provides a way to apply for access rights (e.g. by issuing an API key)

An access token or something like this might be OK.

### 7. The organisation SHOULD grant third parties the same functional scope on the backend as its own clients.

Assessment criteria: The assessor collects complaints (e.g. including screenshots or other "proof") filed by 3rd parties.

### 8. The organisation SHOULD allow third parties to communicate directly with its devices without going through the backend.

Assessment criteria: The organisation provides URL(s) of publicly accessible documentation for all of the following aspects of the device "API"
    - Device "API" (e.g. Bluetooth Profile)
- Protocol (e.g. CoAP, MQTT)
- Data format (e.g. binary encoding)

## Openness

### 1. The organisation MAY publish the device source code under an open source license.
    
Assessment criteria: Files are accessible on inspection. We recommend using MIT License or Apache 2 or GPLv3 licenses for the source code or at least a license compliant with the Open Source Definition (https://opensource.org/docs/osd).

### 1. The organisation MAY publish the device hardware designs under an open hardware license.

Assessment criteria: Files are accessible on inspection.These may include but not limited to schema files, PCB layouts, and any other materials that would support the recreation of the product by the end user. We recommend using a license compliant with the Open Source Hardware Definition (https://www.oshwa.org/definition/). 

### 1. The organisation MAY publish the backend source code under an open source license.

Assessment criteria: Files are accessible on inspection. We recommend using MIT License or Apache 2 or AGPLv3 licenses for the source code or at least a license compliant with the Open Source Definition (https://opensource.org/docs/osd).
Data Governance

### 1. The organisation SHOULD make it possible for customers to turn off the connection to the backend, this might mean that functionality of the device is reduced.

Assessment criteria: The dependency label is included on product or packaging as well as the organisation’s online presence. Use our suggested labelling system.

### 1. The organisation SHOULD NOT degrade or change the current core functionality of the device over the product lifetime.

Assessment criteria: List of core functionality vs. secondary functionality. Access to all commercially accessible versions of products for testing. Test the core functionality on audit.

## Permissions & Ownership

### 1. The organisation MUST give users the ability to transfer ownership of the device. 

    Assessment: TODO

### 1. When ownership of the device is transferred, the new user MUST NOT have access to previous user's data.

    Assessment: TODO

### 1. The organisation SHOULD offer users the ability to export their data. 

    Assessment: TODO

## Transparency 

### 1. The organisation MUST make explicit to the user what the implications of substantially changing usage of the device are. 

    Assessment criteria: Include on product or packaging. Use our labelling system.

### 1. The organisation MUST be explicit as to the expected duration of terms of service

    Assessment criteria: Include on product or packaging. Use our labelling system.

### 1. If the organisation wants to change the length of the term of service, it MUST first ask permission from the customer. 

    Assessment criteria: Terms & conditions changes are communicated to customers and their permission is sought explicitly.

### 1. The organisation MUST inform the user about firmware upgrades.

    Assessment criteria: 
An automated message should be generated or an alert to remind customers how to implement a change in firmware.
Security

### 1. The organisation MUST provide at least minimum cryptographic security on its backend & secure configuration
    Assessment criteria: 
    The product will be tested to check the following:
FDE 
TLSv1.2 on all web-based endpoints
Secure hashing
E.g. Salted bcrypt/scrypt
Secure PII storage
Only necessary ports are exposed to the internet (e.g. no access to debug ports like SSH/Telnet/etc., hadoop ports not open, SMB ports not open, NoSQL/SQL server ports not open, etc. etc.)
Relevant Cookie flags and security headers (web) present where applicable (see OWASP guidelines)

### 1. The organisation’s backend MAY implement additional secure setup options. 

    Assessment criteria: 
The product will be tested to check the following: 
Minimal compliance with OWASP Top 10 (2017) and SANS Top 25 which includes:
No SQLi - adequate protections/query parameterisation/filtering present
Good protection against XSS - adequate filtering present
Strong session management
Good authentication management
Random CSRF tokens that are strongly enforced based on last-issued token
Web Server users should not be running as root/admin
Principle of Least Privilege: API service users should have limited access 
Managed access to data: Do DB users need to write to a DB they only search in? Do DB users have access to DB’s they shouldn’t do?

### 1. The organisation SHOULD implement reliable and appropriate backend patching procedures which should be evidenced. 

Assessment criteria: Patches should be regularly applied to any system that is internet facing as a priority, within a reasonable time frame from patch release. Critical patches, where applicable, should be given priority.

### 1. The organisation MUST enforce a strong user identity policy.

Assessment criteria: The organisation’s sign in process encourages its customers to choose passwords which include alphanumeric characters, special symbols, and are of significant permitted length. These passports should be validated server side. Two factor authentication should be included & support for tokenized 2FA e.g. google authenticator.

### 1. The device SHOULD use strong cryptographic schemes.

    Assessment criteria:
    The product will be tested to make sure it complies with 
Per Device Private Keys
Use known-good cryptographic schemes such as:
AES256-CBC with random IV's
RSA based with key strength of 2048 (ideally 4096) bits
E.g. NaCl for public/private keys
Use demonstrably cryptographically secure TRNG’s/PRNG’s

### 1. The device firmware MUST be compliant with industry security standards.

    Assessment criteria:
    A product will be tested to see if its firmware is compliant with
Usage of latest available SDK’s
Monitor and patch with updates for core backend libraries (e.g. wifi libraries, web servers, XML parsers, etc. etc.), not just SDK updates.
A known-good failsafe firmware should be available
    Fair use of Hardware Security Module
Use of on-chip cryptographic accelerators where available
Use of secure storage options where available
Usage of CRP where available
    Secure Setup
Only necessary ports open/available
All services that handle sensitive data have adequate authentication
No debug ports are available (ssh/telnet/etc.)
No unnecessary services (e.g. FTP, TFTP, SMB, etc.)
Documented moves to detect and block basic brute force attacks (e.g. password bruteforcing, WPS Pixie Dust, service bruteforcing, etc.)
Remove Debug/Development headers from PCB (JTAG/UART/etc.)

### 25. The organisation’s product must be compliant with the IoTSF Security Compliance Framework

Assessment criteria: Relevant compliance class number is published on packaging and online presence of the organisation. 
The organisation must take every precaution to protect usersits customers from the product being exposed to local / adjacent subnet attacks or any other attack. 

### 26. The organisation MUST have clear admin user management policies.

Assessment criteria:
The product will be tested to make sure it is compliant with
Ability and requirement to change Administrator/root access passwords
Device-unique passwords should be loaded into each device at production
Where this is not possible, the admin/root password is to be changed on device first setup or admin first login, whichever happens first
Specific account that hidden backdoor accounts are not to be included on production releases
Limited number of large-scope administration accounts (such as Domain/Enterprise admin accounts)
Lifecycle

### 27. The organisation MUST offer the ability for a user to factory reset the device. 

    Assessment criteria: Device and/or backend has factory reset functionality ?

### 28. The organisation MUST be clear about the expected lifetime of the service provided by the device and backend. 

Assessment criteria: Include on the packaging of the product and on the online presence of the organisation a clear statement of intended lifetime and support. Post-lifetime support should be clearly explained ( replacement part vendor list. An End of Life T&C’s and End of Life actions should be well defined - including in case of bankruptcy, takeover, etc.Should include ‘what happens to my data?’ and ‘what happens to my device(s)?’

### 29. The organisation MUST be clear about the levels of customer support provided during the lifetime of the product. 

    Assessment criteria: description of customer support mechanisms online or on the on the packaging.

### 30. The organisation SHOULD document any parts that a customer can repair using commonly accessible tools and skills.

    Assessment criteria: Publicly available instructions and in an accessible format. STL files should be made available if the piece is expected to be 3D printed. 

### 31. The organisation SHOULD supply spare parts on request during the lifecycle of the product.

    Assessment criteria: A clear and accessible form that a customer can fill in to request these part should be included as part of the packaging or online presence of the organisation. 

### 32. The organisation SHOULD be able to list the geographic regions involved in the supply chain.

    Assessment criteria: Regions example: http://goodnightlamp.com/country-list/

### 33. The organisation SHOULD be able to list at least the first level of suppliers involved in their supply chain.

    Assessment criteria: TODO

# Contributors

Privacy: Mark Simpkins (@marksimpkins), 

Interoperability: Andy Stanford-Clark (@andysc), Boris Adryan (@borisadryan), Peter Robinson (@nullr0ute), Bob van Luijt (@bobvanluijt), Thomas Amberg (@tamberg) 

Openness: Thomas Amberg (@tamberg)

Data Governance: Dr. Alison Powell, Mark Simpkins (@marksimpkins), Selena Nemorin (@digiteracy)

Permissions & Ownership: Martin Dittus (@dekstop), Mark Simpkins (@marksimpkins), Selena Nemorin (@digiteracy) 

Transparency: Pilgrim Beart (@pilgrimbeart)

Security: Mark Carney (@LargeCardinal), Graham Markall (@gmarkall), Jan-Peter Kleinhans (@JPKleinhans), Alasdair Allan (@aallan), Cédric Lévy-Bencheton (@clevybencheton)

Lifecycle: Alasdair Allan (@aallan), Chris Adams (@mrchrisadams), Adrian McEwen (@amcewen), Dries De Roeck (@driesderoeck), Matthew Macdonald-Wallace (@mbconsultinguk), Joanna Montgomery (@joannasaurusrex), Gavin Starks (@agentGav)

Current Version edit by: Alasdair Allan (@aallan), Anthony James Munns (@bitshiftmask), Albrecht Kurze (@AlbrechtKurze), Thomas Amberg (@tamberg), Chris Adams (@mrchrisadams), Alexandra Deschamps-Sonsino (@iotwatch)
