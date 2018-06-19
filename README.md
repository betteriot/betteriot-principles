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
The following definitions are based on a simple [reference model](http://www.tamberg.org/iotmark/2018/ConnectedProductReferenceModel.pdf) for connected products.

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
A _third party_ is everybody else than the vendor or the user.

## Assessment
The assessment criteria below are intended to be "self-assessed but verifiable" and allow "verification through documentation" as specified in [this presentation](https://www.slideshare.net/peterbihr/towards-a-trustmark-for-iot-30-may-2018) by Peter Bihr / ThingsCon (CC BY-SA 4.0).

To enable a central repository, assessment deliverables should be one or more URL links to publicly accessible resources on the vendor (or third party) website, including technical and user documentation, privacy and security policies, terms and conditions, and source code.

## Principles
- [Privacy](#privacy)
- [Interoperability](#interoperability)
- [Openness](#openness)
- [Ownership](#ownership)
- [Transparency](#transparency)
- [Security](#security)
- [Lifecycle](#lifecycle)

## Privacy
Note: What does GDPR compliance mean for IoT? Connected products often collect data through device sensors or by logging user commands. The distinction between personal user data and environmental data becomes fluent. All data is assumed to be personal.

### <strike>1. The connected product the vendor supplies MUST be GDPR compliant.</strike>

<strike>Assessment: GDPR policy is published on the vendor website / a simple checklist is completed. Use our checklist.</strike>

<strike>Example: [GDPR for things](https://www.slideshare.net/sasvangent/gdpr-for-things-thingscon-amsterdam-2017/1)</strike>

### <strike>2. The vendor MUST NOT sell user data without consent.</strike>

<strike>Assessment: TODO</strike>

### <strike>3. User data MUST NOT be used for profiling, marketing or advertising without transparent disclosure and easy opt-out.</strike>

<strike>Assessment: ICA complaint (registration number)</strike>

### ?. The vendor MUST allow users to access their collected data, free of charge.

Assessment: The vendor submits a link to public documentation explaining how to export collected data, and a link to the respective section in terms & conditions.

Example: TODO

### ?. The vendor MUST make clear to users how the collected data is used.

Assessment: The vendor submits a link to its public privacy policy explaining how the collected data is used.

Example: TODO

### ?. The vendor MUST allow users to delete their collected data.

Assessment: The vendor submits a link to public documentation explaining how to delete collected data, to "be forgotten".

Example: TODO

### ?. The vendor MUST allow users to migrate their collected data to another backend.

Assessment: The vendor submits a link to public documentation explaining how to export collected data, and a link to the respective section in terms & conditions.

Example: TODO

### ?. The vendor MUST allow users to easily opt out of direct marketing based on their collected data.

Assessment: The vendor submits a link to public documentation explaining how to opt out of direct marketing based on the collected data.

Example: TODO

### ?. The vendor MUST allow users to restrict the use of their collected data.

Assessment: The vendor submits a link to public documentation explaining how to restrict the use of the collected data.

Example: TODO

### ?. The vendor MUST allow users to update their collected data.

Assessment: The vendor submits a link to public documentation explaining how to update the collected data.

Example: TODO

### ?. The vendor MUST allow users to stop automated decisions being made, if there are personal legal or significant consequences.

Assessment: The vendor submits a link to public documentation explaining how to stop automated decisions and get a human to re-evaluate the decision.

Example: TODO

## Interoperability
Note: Interoperability is about making it technically possible to use devices, backends and clients of the vendor with those of a third party. Interoperability does not imply unrestricted access to user data.

### 4. The vendor SHOULD allow third parties to connect clients to its backend.

Assessment: The vendor submits a link to public documentation of the client-specific backend API.

Example: [Safecast HTTP Client API](https://api.safecast.org/)

    - Endpoint: api.safecast.org:443
    - Protocol: HTTPS
    - Methods: GET /measurements.json, ...
    - Data format: JSON, e.g. Measurement {"value":47.0,"unit":"cpm","captured_at":"2011-04-23T21:53:03.000Z","latitude":35.640968333333,"longitude":139.72069833333}
    - Data model: users, measurements, devices

### 6. The vendor SHOULD grant third party clients the same functional scope on the backend as its own clients.

Assessment: The assessor collects complaints, including screenshots or video "proof", filed by users or third parties.

Example: Some client-specific backend APIs delay measurements they make available to third party clients, preventing them from making real-time decisions.

### 5. The vendor MAY allow third parties to connect devices to its backend.

Assessment: The vendor submits a link to public documentation of the device-specific backend API.

Example: [ThingSpeak MQTT Device API](https://ch.mathworks.com/help/thingspeak/publishtoachannelfeed.html)

    - Endpoint: mqtt.thingspeak.com:8883
    - Protocol: MQTT with TLS
    - Methods: PUB channels/CHANNEL_ID/publish/API_KEY
    - Data format: ASCII, field1=T_VALUE&field2=H_VALUE
    - Data model: channels, measurements, e.g. temperature & humidity

### 7. The vendor SHOULD allow third parties to communicate directly with its devices, without going through the backend.

Assessment: The vendor submits a link to public documentation of the device communication interface.

Example: Generic BLE heart rate sensor

    - Physical communication standard: Bluetooth Low Energy (BLE)
    - Protocol: BLE [GATT](https://www.bluetooth.com/specifications/gatt/generic-attributes-overview)
    - Access primitives: BLE [Heart Rate Profile](https://developer.bluetooth.org/TechnologyOverview/Pages/HRP.aspx)
    - Data format: binary encoding, [heart rate measurement](https://www.bluetooth.com/specifications/gatt/viewer?attributeXmlFile=org.bluetooth.characteristic.heart_rate_measurement.xml&u=org.bluetooth.characteristic.heart_rate_measurement.xml)
    - Data model: heart rate, sensor location, control point

## Openness
Note: Openness is about open source, which is considered a simple way to reduce dependencies between a vendor and a user and build trust between them. Openness does not imply unrestricted access to user data.

### 8. The vendor MAY publish the device firmware source code under an open source license.

Assessment: The vendor submits a link to a public source code repository or ZIP file. The source code is licensed with MIT License or Apache 2 or GPLv3 or at least a license compliant with the [Open Source Definition](https://opensource.org/docs/osd).

Example: [TheThingsNetwork firmware](https://github.com/TheThingsNetwork/arduino-device-lib)

### 9. The vendor MAY publish the device hardware designs under an open hardware license.

Assessment: The vendor submits a link to a public repository or ZIP file. Hardware design files may include but are not limited to schema files, PCB layouts, and any other materials that would support the recreation of the product by the user or a third party. The license is compliant with the [Open Source Hardware Definition](https://www.oshwa.org/definition/).

Example: [Safecast devices](https://github.com/Safecast/General/wiki/Safecast-Devices)

### 10. The vendor MAY publish the backend source code under an open source license.

Assessment: The vendor submits a link to a public repository or ZIP file. The source code is licensed with Apache 2 or AGPLv3 or at least a license compliant with the [Open Source Definition](https://opensource.org/docs/osd).

Example: [TheThingsNetwork backend source code](https://github.com/TheThingsNetwork/ttn)

### ?. The vendor MAY publish client source code under an open source license.

Assessment: The vendor submits a link to a public source code repository or ZIP file. The source code is licensed with MIT License or Apache 2 or GPLv3 or at least a license compliant with the [Open Source Definition](https://opensource.org/docs/osd).

Example: TODO

## Ownership

### 11. The vendor SHOULD allow users to turn off the connection from the device to the backend.

Assessment: The vendor submits a link to user documentation explaining how to turn off the connection from the device to the backend.

Example: TODO

### 13. The vendor MUST allow users to transfer ownership of the device.

Assessment: The vendor submits a link to public user documentation explaining how to transfer ownership of a device to another user.

Example: TODO

### 14. When ownership of the device is transferred, the new user MUST NOT have access to previous user's data.

Assessment: The vendor submits a link to video proof. The assessor collects user complaints.

Example: TODO

### <strike>15. The vendor SHOULD allow users to export their data.</strike>

<strike>Assessment criteria: TODO</strike>

## Transparency

### 16. The vendor MUST make explicit the legal implications of substantially changing device usage.

Assessment: The vendor submits a link to public user documentation explaining the (secondary) legal implications of changing how the device is used, or taking it offline.

Example: Turning off a car's blackbox on the race track might lead to increased insurance fees.

### 17. The vendor MUST make explicit the expected duration of the terms of service.

Assessment: The vendor submits a link to the terms of service which have to include a "best before" expiration date.

Example: TODO

### 18. The vendor MUST ask permission from users before changing the terms of service.

Assessment: The vendor submits proof that terms & conditions changes are communicated to users and their permission is sought explicitly.

Example: TODO

### 19. The vendor MUST inform users about substantial firmware upgrades.

Assessment: The vendor submits a link to a blog or feed or other public, auditable trail of firmware revisions.

Example: TODO

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

### 27. The vendor MUST allow users to factory reset the device.

Assessment: The vendor submits a link to public user documentation showing how to factory reset the device.

Example: TODO

### 28. The vendor MUST be clear about the expected service lifetime of the connected product.

Assessment: Include on the packaging of the product and on the online presence of the vendor a clear statement of intended lifetime and support. Post-lifetime support should be clearly explained ( replacement part vendor list. An End of Life T&C’s and End of Life actions should be well defined - including in case of bankruptcy, takeover, etc. Should include ‘what happens to my data?’ and ‘what happens to my device(s)?’

Example: TODO

### 29. The vendor MUST be clear about the levels of user support provided during the lifetime of the connected product.

Assessment: The vendor submits a link to a public description of user support mechanisms online or on the on the packaging.

Example: TODO

### 12. The vendor SHOULD NOT degrade or change the core functionality of the connected product over its lifetime.

Assessment: Core functionality is declared once by the vendor and backed by submitting marketing materials. Compliance with the principle can be verified on audit or by users at any time by comparing the current functionality with the declared core functionality.

Example: TODO

### 30. The vendor SHOULD document any parts that a user can repair using common tools and skills.

Assessment: The vendor submits a link to public user documentation. Design files should be made available if the piece is expected to be 3D-printed.

Example: TODO

### 31. The vendor SHOULD supply spare parts on request during the lifecycle of the product.

Assessment: A clear and accessible form that a user can fill in to request these parts should be included as part of the packaging or online presence of the vendor.

Example: TODO

### <strike>32. The vendor SHOULD be able to list the geographic regions involved in the supply chain.</strike>

<strike>Assessment: Regions example: http://goodnightlamp.com/country-list/</strike>

### <strike>33. The vendor SHOULD be able to list at least the first level of suppliers involved in their supply chain.</strike>

<strike>Assessment: TODO</strike>

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
