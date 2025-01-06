# Proposed Charter for Network Attestation for Secure Routing (NASR)

## Background and Motivation

In the Internet architecture, communicating entities blindly trust and use paths as determined by the control plane. These available path(s) are assumed to be usable, trustable, performant, and realizing the expected requirements. Communicating entities have very little information about the paths over which their traffic is carried, and have no available means to audit paths, beyond basic properties like latency, throughput, and congestion. However, increased demand in network security, privacy, robustness, and confidentiality makes tools for path properties accountability a necessity.

Path-agnostic traffic signing and encryption has been insofar the primary method to ensure data confidentiality, integrity and authenticity. However, an increasing amount of attacks, vulnerabilities, and new emerging requirements are deeming the data security provided by such methods insufficient. Vulnerable factors include:

* Exploitation of poor cryptographic engineering
* Side-channel attacks
* Untrusted network devices (e.g., middlebox decryption and/or inspection)
* Unauthorized data duplication
* Unauthorized device root access, caused by physical tampering or penetration
* Erroneous routing to unintended devices or areas, etc.

Clients with high security and privacy requirements are not anymore satisfied with pure encryption-based data security measures, having no confidence of the security aspects of the underlying network elements. Clients now require proofs that data traverse through security-satisfying network elements (devices, links and services), avoiding any exposure to unqualifying elements. Clients would like to propose security requirements, such as paths composed of devices with the latest security updates, have passed integrity checks, or routes confined within specific geographical areas. Accordingly, operators should provide verifiable proofs to the clients for operational visualization, internal inspection and external auditing. 

RATS (Remote Attestation Procedures) working group has provided a framework and approaches to assess and establish the trustworthiness of a single device. Several individual submissions are also offering part of the solution to achieve NASR goal. However, a comprehensive framework that attests to a network-- meaning network-level security proofs and verification methods remains elusive.

## Goals and Scope

The Network Attestation for Secure Routing working group is chartered to address the challenges associated with proving security state and characteristics of a network path, so as to achieve reliable/predictable and verifiable forwarding behavior. The work will build on existing standards and implementations, focusing on combining them in a clear and coherent manner to address secure forwarding use cases such as those identified and described in the NASR Use Cases and Requirements document.

The working group will initially focus on a simple source-routing path in limited domains [RFC8799] under a single administrative control. Inter-domain scenario is partially covered to permit interaction between two limited domains, but not the public Internet. Extending NASR across multiple domains and complex topologies will be considered in the future. 

Due to their similarities between RATS and NASR, mainly related to NASR's dependency on RATS outputs, NASR will work closely with RATS working group for collaboration and consultation.  NASR will also take consideration of useful works from concluded working groups, such as I2NSF, SFC. 

## Out of Scope

- Path computation according to client's security requirements (Do-elsewhere)
- Automated operational security incident remediation, routing fault correction.
- Methods of how to assess device integrity. 

## Work Items

- **NASR Use Cases, Problem Statement and Requirements**: As for the title the document will described use cases, formalize their requirement and the problem to be solved. 
    - Candidate document: [draft-liu-nasr-requirements-03](https://datatracker.ietf.org/doc/draft-liu-nasr-requirements/)
- **NASR Architecture**: An architecture document that defines the interactive procedures of network path attestation, along with definitions of common terminology, roles, trust models etc.
    - Candidate document: [draft-liu-nasr-architecture-01](https://datatracker.ietf.org/doc/draft-liu-nasr-architecture/)
- **NASR Service Model**: A document that defines a standard service interface between operators and operator clients, translate client requests to objective security features or trust attributes, making sure the same service request will receive same security levels services from different operators. 
- **Path Attestation Claims Set**: Attested claims set that describes state and characteristics of a network path comprised of network elements. It should be collectively defined by all network elements in the path, and encoded in certain encapsulation formats. This claims set is used by a relying party, to determine if the operator delivers the requested security requirements.
- **Proof of Transit**: Mechanisms and protocol extensions for Proof-of-Transit (PoT), proving and visualizing the actual forwarding paths in the data plane.


## Relation with other WGs

The NASR working group will coordinate and collaborate with other WGs as needed. 
Specific expected interactions include (but may not be limited to):

- RATS on the remote attestation technology.
- PANRG on path-aware networking aspects.
- Other IETF WGs and IRTF RGs that address topics related to attestation, routing security, like for instance SAVNET, SIDROPS.

