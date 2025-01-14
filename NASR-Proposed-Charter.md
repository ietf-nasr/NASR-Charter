# Proposed Charter for Network Attestation for Secure Routing (NASR)

## Background and Motivation

In the current network deployments, communicating entities implicitly rely on peer entities and use paths as determined by the control plane.
These available path(s) are implicitly trusted.
Communicating entities have very little information about the entities in the paths over which their traffic is carried, and have no available means to audit the entities and paths, beyond basic properties like latency, throughput, and congestion.
However, increased demand in network security, privacy, and robustness makes tools for enabling visibility of the entities' security posture a necessity.

Path-agnostic traffic signing and encryption has been the primary method to ensure data confidentiality, integrity and authenticity today.
However, with the increasing amount of attacks, and vulnerabilities, new emerging threats are imposing requirements that go beyond the data security currently provided.
Vulnerable factors include:

* Exploitation of poor cryptographic engineering
* Side-channel attacks
* Untrusted network devices (e.g., middlebox decryption and/or inspection)
* Unauthorized data duplication
* Unauthorized device root access, caused by physical tampering or penetration
* Erroneous routing to unintended devices or areas, etc.

With these additional security and privacy requirements, there is a need to provide enhanced or added services beyond the pure encryption-based data security; requiring better visibility of the security posture of the underlying network elements.
Specifically, to satisfy the visibility of the network elements' security state, proof that data is traversed through network elements (devices, links and services) that satisfy security posture claims to avoid exposure of unqualified elements is needed.

The RATS (Remote ATtestation procedureS) working group has provided a framework and approaches to assess and establish the trustworthiness of a single device, hence offering an initial building block.
However, a comprehensive framework that attests to a network -- meaning network-level elements' trustworthiness proofs and verification methods are lacking.

## Goals

The Network Attestation for Secured FoRwarding working group is chartered to address the challenges associated with proving state and characteristics of a network path are compliant to a set of claims, so as to achieve predictable and verifiable forwarding behavior. 
The work will build as much as possible on existing standards and implementations, focusing on combining them in a clear and coherent manner to address secured forwarding use cases such as those identified and described in the NASR use cases and requirements document.

The working group will initially focus on a simple source-routing path in limited domains [RFC8799] under a single administrative control.
The working group will then focus on a simple source-routing path spanning a few numbers of limited domains that have business relationship, in order to help coordinate, connect and deliver a consistent connectivity service.
Applying NASR to large groups of domains such as the Internet is not seen as viable and useful use case.

## Work Items

- **NASR Use Cases, Problem Statement and Requirements**: As for the title the document will described use cases, formalize their requirements and the problem to be solved, including a threat analysis. 
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


## Out of Scope

- Path computation according to a set of claims.
- Automated operational security incident remediation, routing fault correction.
- Methods of how to assess device integrity and/or trust-level.
- Public Internet deployment.
- Proof of non-transit.
