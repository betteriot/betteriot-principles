# IoT Mark Principles
Open IoT Certification Mark Principles – June 13th 2018

## License
This work by [iotmark.org](http://iotmark.org/) is licensed under [Creative Commons BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/).

## Introduction
This is the latest version of a working document to develop [a certification mark for connected products](http://iotmark.wordpress.com/) by IoT community members worldwide. This is a work in progress and you may [comment](https://github.com/openiotmark/iotmark-principles/issues) freely, join the conversation on [Slack](https://join.slack.com/iotmark/shared_invite/MjA5MjQzMTM0ODg2LTE0OTkyOTI1MDItY2JjODI3OWNmNQ), [sign up to our newsletter](http://designswarm.us4.list-manage.com/subscribe?u=2101384e03af780d68370fb40&id=f898782217) or give us feedback in writing (alex@iot.london) or on our [monthly open calls](https://calendar.google.com/calendar/ical/designswarm.com_2v6ddgu2m907s0ohe5c1upceqg%40group.calendar.google.com/public/basic.ics).

This is a set of principles that we think a vendor — a connected product manufacturer, team or founder — would use to make a good, secure, ethical, product that also takes into account the General Data Protection Regulation (GDPR). But also to push beyond the GDPR and look at the entire life cycle of a smart device. From manufacture, to final disposal.

## Terminology
The terminology in this document is a bit technical, bear with us. We use _MUST_, _SHOULD_, and _MAY_ because of a technical writing standard called [RFC 2119](https://www.ietf.org/rfc/rfc2119.txt).

## Definitions
Based on this simple [reference model](http://www.tamberg.org/iotmark/2018/ConnectedProductReferenceModel.pdf) for connected products.

### Connected Product
A _connected product_ is the entirety of one or more devices, gateways, a backend, apps and the services they represent.

### Device
A _device_ is a physical thing with connectivity, an embedded computer, sensors and actuators. (A client running a dashboard app is not a device in this sense.)

### Gateway
A _gateway_ is a physical device, often bridging physical transports to connect devices to the backend. It might aggregate data, or enact local control.

### Backend
The device is connected to a _backend_, consisting of one or more server(s) "in the cloud". The connection is established over the Internet, sometimes via a gateway.

### Client
A _client_ is any app, dashboard or third party service. Once a device is connected, it allows for virtual interaction, often through a backend API.

### API
An _API_ is an application programming interface. It defines an endpoint, a protocol and a data format. The backend API allows devices or clients to programmatically talk to the backend.

## Roles

### Vendor
The _vendor_ builds, sells or operates the connected product and implements the IoT Mark principles. The term is not very concise, but seems more accurate than manufacturer, seller, integrator, maintainer or service operator.

### User
The _user_ buys, owns or uses the connected product. The term is quite broad, but seems more fitting than consumer, customer, owner or data subject.

### Third party
A _third party_ is anybody else than the vendor or the user.

## Principles
- [Privacy](#privacy)
- [Interoperability](#interoperability)
- [Openness](#openness)
- [Data Governance](#data-governance)
- [Permissions & Ownership](#permissions--ownership)
- [Transparency](#transparency)
- [Security](#security)
- [Lifecycle](#lifecycle)

## Assessment
The assessment criteria below are intended to be "self-assessed but verifiable" and allow "verification through documentation" as specified in [this presentation](https://www.slideshare.net/peterbihr/towards-a-trustmark-for-iot-30-may-2018) by Peter Bihr / ThingsCon (CC BY-SA 4.0).

## Privacy

### 1. The connected product the vendor supplies MUST be GDPR compliant.

    Assessment: GDPR policy is published on the vendor website / a simple checklist is completed. Use our checklist.

### 2. The vendor MUST NOT sell customer data without consent.

    Assessment: TODO

### 3. Their customer data MUST NOT be used for profiling, marketing or advertising without transparent disclosure and easy opt-out.

    Assessment: ICA complaint (registration number)

## Interoperability

### 4. The vendor SHOULD allow third parties to connect clients to its backend.

Assessment: The vendor submits links to public documentation of the client-specific backend API.

Example: [Safecast HTTP Client API](https://api.safecast.org/)

    - Endpoint: api.safecast.org:443
    - Protocol: HTTPS
    - Methods: GET /measurements.json, ...
    - Data Format: JSON, e.g. Measurement {"value":47.0,"unit":"cpm","captured_at":"2011-04-23T21:53:03.000Z","latitude":35.640968333333,"longitude":139.72069833333}
    - Data Model: Users, Measurements, Devices

### 6. The vendor SHOULD grant third parties the same functional scope on the backend as its own clients.

Assessment: The assessor collects complaints (e.g. including screenshots or other "proof") filed by third parties.

### 5. The vendor MAY allow third parties to connect devices to its backend.

Assessment: The vendor submits links to public documentation of the device-specific backend API.

Example: [ThingSpeak MQTT Device API](https://ch.mathworks.com/help/thingspeak/publishtoachannelfeed.html)

    - Endpoint: mqtt.thingspeak.com:8883
    - Protocol: MQTT with TLS
    - Methods: PUB channels/CHANNEL_ID/publish/API_KEY
    - Data Format: ASCII, field1=T_VALUE&field2=H_VALUE
    - Data Types: Channels, Measurements, e.g. Temperature & Humidity

### 7. The vendor SHOULD allow third parties to communicate directly with its devices without going through the backend.

    Assessment: The vendor submits links to public documentation of the device communication interface.

Example: (TODO)

    This includes the physical communication standard (e.g. Bluetooth radio), access primitives (e.g. Bluetooth Profile), protocol (e.g. CoAP, MQTT) and payload data format (e.g. binary encoding).

## Openness

### 8. The vendor MAY publish the device source code under an open source license.

    Assessment criteria: Files are accessible on inspection. We recommend using MIT License or Apache 2 or GPLv3 licenses for the source code or at least a license compliant with the Open Source Definition (https://opensource.org/docs/osd).

### 9. The vendor MAY publish the device hardware designs under an open hardware license.

    Assessment criteria: Files are accessible on inspection.These may include but not limited to schema files, PCB layouts, and any other materials that would support the recreation of the product by the end user. We recommend using a license compliant with the Open Source Hardware Definition (https://www.oshwa.org/definition/).

### 10. The vendor MAY publish the backend source code under an open source license.

    Assessment criteria: Files are accessible on inspection. We recommend using MIT License or Apache 2 or AGPLv3 licenses for the source code or at least a license compliant with the Open Source Definition (https://opensource.org/docs/osd).

## Data Governance

### 11. The vendor SHOULD make it possible for customers to turn off the connection to the backend, this might mean that functionality of the device is reduced.

    Assessment criteria: The dependency label is included on product or packaging as well as the vendor’s online presence. Use our suggested labelling system.

## Permissions & Ownership

### 13. The vendor MUST give users the ability to transfer ownership of the device.

    Assessment criteria: TODO

### 14. When ownership of the device is transferred, the new user MUST NOT have access to previous user's data.

    Assessment criteria: TODO

### 15. The vendor SHOULD offer users the ability to export their data.

    Assessment criteria: TODO

## Transparency

### 16. The vendor MUST make explicit to the user what the implications of substantially changing usage of the device are.

    Assessment criteria: Include on product or packaging. Use our labelling system.

### 17. The vendor MUST be explicit as to the expected duration of terms of service

    Assessment criteria: Include on product or packaging. Use our labelling system.

### 18. If the vendor wants to change the length of the term of service, it MUST first ask permission from the customer.

    Assessment criteria: Terms & conditions changes are communicated to customers and their permission is sought explicitly.

### 19. The vendor MUST inform the user about firmware upgrades.

    Assessment criteria: An automated message should be generated or an alert to remind customers how to implement a change in firmware.

## Security

### 20. The vendor MUST provide at least minimum cryptographic security on its backend & secure configuration

    Assessment criteria:
    The product will be tested to check the following:
    - FDE
    - TLSv1.2 on all web-based endpoints
    - Secure hashing
        - E.g. Salted bcrypt/scrypt
    - Secure PII storage
        - Only necessary ports are exposed to the internet (e.g. no access to debug ports like SSH/Telnet/etc., hadoop ports not open, SMB ports not open, NoSQL/SQL server ports not open, etc. etc.)
        - Relevant Cookie flags and security headers (web) present where applicable (see OWASP guidelines)

### 21. The vendor’s backend MAY implement additional secure setup options.

    Assessment criteria:
    The product will be tested to check the following:
    - Minimal compliance with OWASP Top 10 (2017) and SANS Top 25 which includes:
        - No SQLi - adequate protections/query parameterisation/filtering present
        - Good protection against XSS - adequate filtering present
        - Strong session management
        - Good authentication management
        - Random CSRF tokens that are strongly enforced based on last-issued token
    - Web Server users should not be running as root/admin
    - Principle of Least Privilege: API service users should have limited access
    - Managed access to data: Do DB users need to write to a DB they only search in? Do DB users have access to DB’s they shouldn’t do?

### 22. The vendor SHOULD implement reliable and appropriate backend patching procedures which should be evidenced.

    Assessment criteria: Patches should be regularly applied to any system that is internet facing as a priority, within a reasonable time frame from patch release. Critical patches, where applicable, should be given priority.

### 23. The vendor MUST enforce a strong user identity policy.

    Assessment criteria: The vendor’s sign in process encourages its customers to choose passwords which include alphanumeric characters, special symbols, and are of significant permitted length. These passports should be validated server side. Two factor authentication should be included & support for tokenized 2FA e.g. google authenticator.

### 24. The device SHOULD use strong cryptographic schemes.

    Assessment criteria:
    The product will be tested to make sure it complies with
    - Per Device Private Keys
    - Use known-good cryptographic schemes such as:
        - AES256-CBC with random IV's
        - RSA based with key strength of 2048 (ideally 4096) bits
        - E.g. NaCl for public/private keys
    - Use demonstrably cryptographically secure TRNG’s/PRNG’s

### 25. The device firmware MUST be compliant with industry security standards.

    Assessment criteria:
    A product will be tested to see if its firmware is compliant with
    - Usage of latest available SDK’s
    - Monitor and patch with updates for core backend libraries (e.g. wifi libraries, web servers, XML parsers, etc. etc.), not just SDK updates.
    - A known-good failsafe firmware should be available
    - Fair use of Hardware Security Module
        - Use of on-chip cryptographic accelerators where available
        - Use of secure storage options where available
        - Usage of CRP where available
    - Secure Setup
        - Only necessary ports open/available
        - All services that handle sensitive data have adequate authentication
        - No debug ports are available (ssh/telnet/etc.)
        - No unnecessary services (e.g. FTP, TFTP, SMB, etc.)
        - Documented moves to detect and block basic brute force attacks (e.g. password bruteforcing, WPS Pixie Dust, service bruteforcing, etc.)
        - Remove Debug/Development headers from PCB (JTAG/UART/etc.)
        - The vendor’s product must be compliant with the IoTSF Security Compliance Framework
        - Relevant compliance class number is published on packaging and online presence of the vendor.
        - The vendor must take every precaution to protect usersits customers from the product being exposed to local / adjacent subnet attacks or any other attack.

### 26. The vendor MUST have clear admin user management policies.

    Assessment criteria:
    The product will be tested to make sure it is compliant with
    - Ability and requirement to change Administrator/root access passwords
    - Device-unique passwords should be loaded into each device at production
        - Where this is not possible, the admin/root password is to be changed on device first setup or admin first login, whichever happens first
    - Specific account that hidden backdoor accounts are not to be included on production releases
    - Limited number of large-scope administration accounts (such as Domain/Enterprise admin accounts)

## Lifecycle

### 27. The vendor MUST offer the ability for a user to factory reset the device.

    Assessment criteria: Device and/or backend has factory reset functionality ?

### 28. The vendor MUST be clear about the expected lifetime of the service provided by the device and backend.

    Assessment criteria: Include on the packaging of the product and on the online presence of the vendor a clear statement of intended lifetime and support. Post-lifetime support should be clearly explained ( replacement part vendor list. An End of Life T&C’s and End of Life actions should be well defined - including in case of bankruptcy, takeover, etc.Should include ‘what happens to my data?’ and ‘what happens to my device(s)?’

### 29. The vendor MUST be clear about the levels of customer support provided during the lifetime of the product.

    Assessment criteria: description of customer support mechanisms online or on the on the packaging.

### 12. The vendor SHOULD NOT degrade or change the current core functionality of the connected product over its lifetime.

    Assessment: Core functionality is declared once by the vendor and backed by submitting marketing materials. Compliance with the principle can be verified on audit or by users at any time by comparing the current functionality with the declared core functionality.

### 30. The vendor SHOULD document any parts that a customer can repair using commonly accessible tools and skills.

    Assessment criteria: Publicly available instructions and in an accessible format. STL files should be made available if the piece is expected to be 3D printed.

### 31. The vendor SHOULD supply spare parts on request during the lifecycle of the product.

    Assessment criteria: A clear and accessible form that a customer can fill in to request these part should be included as part of the packaging or online presence of the vendor.

### 32. The vendor SHOULD be able to list the geographic regions involved in the supply chain.

    Assessment criteria: Regions example: http://goodnightlamp.com/country-list/

### 33. The vendor SHOULD be able to list at least the first level of suppliers involved in their supply chain.

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

Berlin March 2018 edit by: Alasdair Allan (@aallan), Anthony James Munns (@bitshiftmask), Albrecht Kurze (@AlbrechtKurze), Thomas Amberg (@tamberg), Chris Adams (@mrchrisadams), Alexandra Deschamps-Sonsino (@iotwatch)

London June 2018 edit by: Alexandra Deschamps-Sonsino (@iotwatch), Thomas Amberg (@tamberg), @Ignius_IoT, Laura James (@LaurieJ), Albrecht Kurze (@AlbrechtKurze), Viktor Petersson (@vpetersson), Alasdair Allan (@aallan), Duncan Wilson (@djdunc), Dom Guinard (@domguinard), Geusseppe Gonzalez (@GeuseppeGC), Dries De Roeck (@driesderoeck), Konrad Komorowski, Alison Powell (@a_b_powell), Mark (@ukmoose), Louise Hugen (@louisehugen), Funda Ustek-Spilda (@fundaustek), Alex Kosenkov
