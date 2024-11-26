# Proposed Charter for Network Attestation for Secure Routing (NASR)

## Background and Motivation

Traffic signing and encryption has been insofar the primary method to ensure data confidentiality, integrity and authenticity. However, an increasing amount of attacks,  vulnerabilities, and new emerging requirements are deeming the data security provided by such methods insufficient. Vulnerable factors include:

* Exploitation of poor cryptographic engineering
* Side-channel attacks
* Untrusted network devices (e.g., middlebox decryption and/or inspection)
* Unauthorized data duplication
* Unauthorized device root access, caused by physical tampering or penetration
* Erroneous routing to unintended devices or areas, etc.


Clients with high security and privacy requirements are not anymore satisfied with pure encryption-based data security measures, having no confidence of the trustworthiness of the underlay networks. Clients require their data to traverse exclusively through trusted devices, trusted links and trusted services, avoiding any exposure to insecure or untrusted devices. Additionally, the clients may also request specific trust requirements, such as paths composed of devices with the latest security updates or routes confined within specific geographical areas. Hence, how to establish routing trustworthiness and transparency so as to achieve predictable and provable forwarding behaviors becomes the main challenge. Verifiable proofs should also be given to serve as a trusted evidence for operational visualization, internal inspection and external auditing. 

RATS (Remote Attestation Procedures) working group has provided a framework and approaches to assess and establish the trustworthiness of a single device. Several individual submissions are also offering part of the solution to achieve NASR goal. However, a comprehensive framework that allows network trust appraisal, trust-aware routing or packet steering, and provide verifiable proof of forwarding, remains elusive. 

## Goals and Scope

The Network Attestation for Secure Routing working group is chartered to address the challenges associated with routing data on top of trusted devices, trusted operating environments, trusted links and trusted services only, so as to achieve transparent, predictable, and verifiable forwarding behavior. The work will build on existing standards and implementations, focusing on combining them in a clear and coherent manner to address secure routing use cases such as those identified and described in the NASR Use Cases and Requirements document.

The working group will initially focus on solutions for limited domain [RFC8799] networks that is under a single administrative control. Inter-domain scenario is partially covered to permit interaction between two limited domains, but not the public Internet. Extending NASR across multiple domains will be considered in the future. 

Due to their similarities between RATS and NASR, mainly related to the notion of trust, and also NASR's dependency on RATS outputs, NASR will work closely with RATS working group for collaboration and consultation.  NASR will also take consideration of useful works from concluded working groups, such as I2NSF, SFC. 

## Out of Scope

- Automated operational security incident remediation, routing fault correction.
- Methods of how to assess device integrity. 

## Work Items

- **NASR Use Cases, Problem Statement and Requirements**: As for the title the document will described use cases, formalize their requirement and the problem to be solved. 
    - Candidate document: [draft-liu-nasr-requirements-01](https://datatracker.ietf.org/doc/draft-liu-nasr-requirements/)
- **NASR Architecture**: An architecture document that defines the interactive procedures of network path attestation, along with definitions of common terminology, roles, trust models etc. 
- **NASR Service Model**: A document that defines a standard service interface between operators and operator clients, translate client requests to objective security features or trust attributes, making sure the same service request will receive same levels of trusted services from different operators. 
- **Path-level Trust Attributes**: collectively defined by all devices or services in the path through attribute aggregation or mapping.
- **Continuous Assurance**: Mechanisms and protocol extensions for verifiable operational correctness evidence, including Proof-of-Transit (PoT), signed device integrity snapshot and/or access log, etc. 

## Dependencies and Liaisons 

The NASR working group will closely collaborate with: 

- Other IETF Working Groups that address topics related to attestation and routing security, including but not limited to, RATS, SAVNET, SIDROPS, IDR.
- Other IRTF Research Groups that provide research inputs and reviews, such as PANRG, CFRG. 
- The European Telecommunications Standards Institute (ETSI), particularly with regard to the Topology Attestation.
- The International Telecommunication Union (ITU), particularly with regard to the Y.TRUST-TLA project (Framework of Trust-Level Assessment for Trustworthy Networking) and ITU-T-SG-13. 

