# Domain 1 - General Security Concepts

## Security Controls
Technical Security Controls /Logical Security Controls
Managerial Security Controls
Operational Security Controls 
Physical Security Controls 

Control Types 
	Preventative 
	Deterrent 
	Detective 
	Directive 
	Compensating 
	Corrective
## CIA Triad
CIA / AIC

Confidentiality 
	- Encryption of messages sent to different people
	- Access Control
	- 2FA
Integrity
	- Non-repudiation 
Availability 
	-Redundancy 
	-Fault Tolerance
	-Patching

## AAA : The Triple A Framework
Authentication -Who you are
Authorization  -What you can have
Accounting -Resources used

## Non-Repudiation
Information Technology's version "No take backs" 

## Gap Analysis
- Where you are and where you want to be 
## Zero Trust
.A holistic approach to network security where nothing is trusted and everything is verified 

Data Plane - process frame, packets, network data , encrypting and NAT(Network Address Translation)
Control Plane - manages actions of the control plane 

Policy Enforcement Point (PEP) The gatekeeper for subjects and systems 
Policy Decision Point (D)) Makes authentication 
	Policy Engine - evaluates each aces decision based off of Policy 
	Policy Administrator - Communicates with PEP and tells it to allow deny or revoke access
	Generates access tokens or credentials

# Deception and Disruption
- Honeypots
- Honeynets
- Honeyfiles
- Honeytokens

## Change Management
Allow List - nothing runs unless approved 
Deny List - everything can run unless stated 

## Public Key Infrastructure 
-Polices, procedures, hardware, software, people associated with creating, distributing , managing storing and revoking digital signatures 

## Encryption
Symmetric Encryption - Uses a single share key 

Asymmetric Encryption(Public Key Encryption) 
- uses two or more mathematically related keys 
- consists of a public key and private key 

Key Escrow - someone else holds your decryption keys 

Transparent encryption - encrypt all DB info with a symmetric key

Record level encryption - encrypt individual columns. Use separate symmetric keys for individual columns 

Transport Encryption - used to protect data traversing a network 

DES - Digital Encryption Standard 
AES - Advanced Encryption Standard 

Key Stretching - make a weak password stronger by hashing it. Hashing that hash and so on.

Key Exchange
	-Out-of-band key exchange : Doesn't send symmetric key e.g. courier or "movie villain briefcase"
	-In-band key exchange : key exchange in a network 

Session Keys are Ephemeral Keys 

Trusted Platform Module (TPM) is  hardware specification used for cryptographic functions 
Hardware Security Module(HSM) is used in large environments with a need for key back backup and cryptographic accelerators 

Obfuscation is the process of making something unclear
Steganography is the Greek word for concealed writing and in cybersecurity it is security through obscurity

Tokenisation - replace sensitive data with non-sensitive data
Data Masking - Hide some of the data e.g. CC XXXX XXXX XXXX 5876

MD5 is an old hashing algorithm with a collision problem 

Rainbow Table - used to try get an original password from a hash
Blockchain - a distributed ledger that keeps track of transactions 

## Certificates 
Digital certificates bind a public key certificate to a CA 
Certificate Signing Request(CSR)- create a key pair then send the public key to be signed by the CA 

Wildcard Certificates 
	Subject Alternative Name (SAN)
	-extension to X.509 certificate 
	-allows a certificate to support many different domains 
OCSP Stapling 
	Online Certificate Status Protocol Stapling 
	Used to scale certificate checks 
CRL - Certificate Revocation List 


