# IoT Mark Principles
(Manually synced mirror of GDoc; to comment, [file an issue](https://github.com/openiotmark/iotmark-principles/issues))
 
Open IoT Certification Mark Principles – October 18th 2017

Draft edited by [@iotwatch](https://twitter.com/iotwatch)

## Privacy
Contributors: [@marksimpkins](https://twitter.com/marksimpkins) 

### 1. The product or service the company supplies MUST be General Data Protection Regulation (GDPR) compliant. 

The company should make sure customers are able gain access to information about the use of their data (e.g how the data is processed, insights generated from the data). 
The company offers customers the right to delete their data and metadata.
Customers are given the ability to selectively withdraw permissions of use of their data (entitlements) temporarily or permanently. In response to this, the company can selectively withdraw access to select services to consumers based on the entitlement level that a consumer provided.

Assessment criteria: GDPR policy is published on the company website / a simple checklist is completed. Use our checklist. The company website publishes a form where a customer can request the deletion of their account and history. The company website offers customers the choice to switch on or off core or secondary functionalities and are clear about the impact of those choices. 

### 2. The company SHALL NOT utilise their products to sell customer data to third parties without the knowledge of their customers. Their customer’s data SHALL NOT be used for profiling, marketing or advertising without transparent disclosure. 

Assessment criteria: ICA compliant (registration number)

## Interoperability
Contributors: [@andysc](https://twitter.com/andysc), [@borisadryan](https://twitter.com/borisadryan), [@nullr0ute](https://twitter.com/nullr0ute), [@bobvanluijt](https://twitter.com/bobvanluijt), [@tamberg](https://twitter.com/tamberg)

### 3. The company MUST allow third parties to connect devices, apps and services to its backend API. 

Assessment criteria: The company provides URL(s) of publicly accessible documentation of the backend Application Programming Interface (API) for all of the following aspects:
- Endpoints (e.g. api.example.com)
- API (e.g. GET /things, e.g. described with Swagger)
- Protocol (e.g. HTTP, MQTT, ...)
- Data format (e.g. JSON, XML; clearly defined data types)
- Data model / information model (e.g. service topics, how to measure temperature)
The company provides a way to apply for access rights (e.g. by issuing an API key)

### 4. The company SHOULD grant third parties the same functional scope on the backend as its own devices, apps and services.

Assessment criteria: The assessor collects complaints (e.g. including screenshots or other "proof") filed by 3rd parties.

### 5. The company MUST allow third parties to communicate with its devices.

Assessment criteria: The company provides URL(s) of publicly accessible documentation for all of the following aspects of the device "API"
- Device "API" (e.g. Bluetooth Profile)
- Protocol (e.g. CoAP, MQTT)
- Data format (e.g. binary encoding)

## Openness
Contributors: [@tamberg](https://twitter.com/tamberg), ...

### 6. The company SHOULD publish the device source code under an open source license.
	
Assessment criteria: Files are accessible on inspection. We recommend using MIT License or Apache 2 or GPLv3 licenses for the source code or at least a license compliant with the Open Source Definition (https://opensource.org/docs/osd).

### 7. The company SHOULD publish the device hardware designs under an open hardware license.

Assessment criteria: Files are accessible on inspection.These may include but not limited to schema files, PCB layouts, and any other materials that would support the recreation of the product by the end user. We recommend using a license compliant with the Open Source Hardware Definition (https://www.oshwa.org/definition/). 

## Data Governance
Contributors: Dr. Alison Powell, [@marksimpkins](https://twitter.com/marksimpkins), [@digiteracy](https://twitter.com/digiteracy)

### 8. The company SHOULD make it visible to its customers what data and channels of communication the device / service uses.

Assessment criteria: Labelling is applied on packaging or product and online presence indicating in plain language the data flow. Use our suggested labelling system.

### 9. The company MUST/SHOULD make it possible for customers to turn off the connection/s to any data cloud. They should make clear the ‘risk’ associated with doing this.

Assessment criteria: The dependancy label is included on product or packaging as well as the company’s online present. Use our suggested labelling system.

### 10. The company MUST/SHOULD? not degrade/change the current core functionality of the device in the future, offering the same core product functionality throughout the natural life of the product. The company MUST not actively reduce core functionality through the natural life of the product. 

Assessment criteria: List of core functionality vs. secondary functionality. Access to all commercially accessible versions of products for testing. Test the core functionality on audit.

## Permissions, Entitlement
Contributors: [@dekstop](https://twitter.com/dekstop), [@marksimpkins](https://twitter.com/marksimpkins), [@digiteracy](https://twitter.com/digiteracy)

### 11. Switch guarantee - A company SHOULD offer customers the right to transfer ownership of hardware, to export their data, and to migrate service providers.

Assessment criteria: Your website publishes a form where customers can request a change of ownership (change of user associated with the hardware), data export and service provider change.
Transparency Contributors: Pilgrim Beart

### 12. A company MUST be explicit to a customer as to whether there are secondary legal obligations, e.g. if they’re buying car insurance via a monitoring device, they might have an obligation to provide valid data.

Assessement criteria: Include on product or packaging. Use our labelling system.

### 13. The company MUST be explicit as to the expected duration of terms (e.g. for how many years is device support guaranteed?)

Assessement criteria: Include on product or packaging. Use our labelling system.

### 14. If a company wants to change the above, it MUST first ask permission from the customer (not just notify, or silently change terms).

Assessment criteria: Terms & conditions changes are communicated to customers and their permission is sought explicitly.

## Security
Contributors: [@LargeCardinal](https://twitter.com/LargeCardinal), [@gmarkall](https://twitter.com/gmarkall), Jan-Peter Kleinhans

### 15. The company MUST provide minimum cryptographic security on its servers & secure configuration
A company’s customers should be protected and the security of their products should be a priority in the development cycle. 

Backend Service Systems:

Assessment criteria: 
	The product will be tested to check the following:
FDE 
TLSv1.2 on all web-based endpoints
Secure hashing
E.g. Salted bcrypt/scrypt
Secure PII storage
Only necessary ports are exposed to the internet (e.g. no access to debug ports like SSH/Telnet/etc., hadoop ports not open, SMB ports not open, NoSQL/SQL server ports not open, etc. etc.)
Relevant Cookie flags and security headers (web) present where applicable (see OWASP guidelines)

### 16. The company’s backend service systems  MUST implement additional secure setup options (aka Defence In Depth) 

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

### 17. The company SHOULD implement reliable and appropriate patching procedures which should be evidenced. Patches should be regularly applied to any system that is internet facing as a priority, within a reasonable time frame from patch release. Critical patches, where applicable, should be given priority.

Assessment criteria:
The product will be tested to check the following:
User-land back-end service requirements (web or mobile apps - hosted):

### 18. The company MUST enforce a strong user identity policy

Assessment criteria: The company’s sign in process encourages its customers to choose passwords which include alphanumeric characters, special symbols, and are of significant permitted length. These passports should be validated server side. Two factor authentication should be included & support for tokenized 2FA e.g. google authenticator.
Device Specific Requirements:

### 19. The company’s product MUST be compliant with the IoTSF Security Compliance Framework

Assessment criteria: Relevant compliance class number is published on packaging and online presence of the company. 

### 20. The company’s product MUST use cryptographic schemes

Assessment criteria:
The product will be tested to make sure it complies with 
Per Device Private Keys
Use known-good cryptographic schemes such as:
AES256-CBC with random IV's
RSA based with key strength of 2048 (ideally 4096) bits
E.g. NaCl for public/private keys
Use demonstrably cryptographically secure TRNG’s/PRNG’s

### 21. The company’s firmware MUST be compliant with industry security standards.

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

### 22. The company MUST clearly communicate with a customer in the event of a change in firmware

Assessment criteria: 
An automated message should be generated or an alert to remind customers how to implement a change in firmware.

### 23. The company MUST clearly communicate with a customer in the event of opting out of Automated Patching 

Assessment criteria: A clear and accessible message should be sent to a customer explaining the implications of doing this in clear language. 

### 24. The company MUST have clear admin user management policies. 

Assessment criteria:
The product will be tested to make sure it is compliant with
Ability and requirement to change Administrator/root access passwords
Device-unique passwords should be loaded into each device at production
Where this is not possible, the admin/root password is to be changed on device first setup or admin first login, whichever happens first
Specific account that hidden backdoor accounts are not to be included on production releases
Limited number of large-scope administration accounts (such as Domain/Enterprise admin accounts)

### 25. The company MUST offer the ability for a customer to do a factory reset on its product. 

Assessment criteria: ?

### 26. The company MUST take every precaution to protect its customers from the product being exposed to local / adjacent subnet attacks or any other attack. 

Assessment criteria: 
The product will be tested for the following:
Restricted physical access to production systems
A 'first-pentest' with a follow-up action plan for resolving the results of the pentest.
Ability to lock devices to hardware security tokens e.g. yubikeys (This can act in place of per-device passwords/private keys)
Strong physical security
Ability to filter by source IP on device
A working Disaster Recovery plan, Vulnerability Disclosure plan, and Breach Response Plan
(Breach Response should have relevant technical, business, and legal contacts within it
You should know if/when you were hacked
You should know what to do
Disclosure Response should exist, and have relevant technical, business, and legal contacts, as well as a workflow for how to raise tickets, assess severity, etc.
Disaster Recovery should be tested regularly e.g. to ensure backup restoration works)
A planned introduction of monitoring software with alerts generated for the right people

## Lifecycle, provenance, sustainability & futureproofing
Contributors: [@aallan](https://twitter.com/aallan), [@mchrisadams](https://twitter.com/mchrisadams), [@amcewen](https://twitter.com/amcewen), [@driesderoeck](https://twitter.com/driesderoeck), [@mbconsultinguk](https://twitter.com/mbconsultinguk), [@joannasaurusrex](https://twitter.com/joannasaurusrex), [@agentGav](https://twitter.com/agentGav)

### 27. The company MUST be clear about the expected lifetime of the product and the expected support the customer should expect. 

Assessment criteria:
Include on the packaging of the product and on the online presence of the company a clear statement of intended lifetime and support. Post-lifetime support should be clearly explained ( replacement part vendor list. An End of Life T&C’s and End of Life actions should be well defined - including in case of bankruptcy, takeover, etc.Should include ‘what happens to my data?’ and ‘what happens to my device(s)?’

### 28. The company MUST document any parts that a customer could be realistically expected to repair.  

Assessment criteria: Publicly available instructions and in an accessible format. STL files should be made available if the piece is expected to be 3D printed. 

### 29. The company MUST supply spare parts on request during the lifecycle of the product.

Assessment criteria: A clear and accessible form that a customer can fill in to request these part should be included as part of the packaging or online presence of the company. 

### 30. The company SHOULD be able to list the countries involved in their supply chain comprising their product.

Assessment criteria: A clear and accessible mention should be included as part of the packaging or online presence of the company.
