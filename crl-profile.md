
## CRL Profile

| **Field** |       |       | **Value**                             |
| :-------- | :---: | :---: | :-------------------------------     |
| Version   |       |       | V2 (1)                                 |
| Issuer Signature Algorithm   |       |       |  sha256 WithRSAEncryption {1 2 840 113549 1 1 11}  |
| Issuer Distinguished Name   |       |       |  Distinguished Name of the CA Issuer |
| thisUpdate   |       |       | Encoded as UTCTime for dates through 2049 and GeneralizedTime for dates thereafter <br> See Section 4.9.7 for publishing intervals.  |
| nextUpdate   |       |       | Encoded as UTCTime for dates through 2049 and GeneralizedTime for dates thereafter <br> See Section 4.9.7 for validity period intervals. |
| Revoked Certificates List   |       |       |  0 or more 2-tuple of certificate serial number and revocation date (Expressed in UTCTime for dates until end of 2049 and GeneralizedTime for dates thereafter )  |
| Issuer Signature   |       |       |   sha256 WithRSAEncryption {1 2 840 113549 1 1 11}    |
|               |                 |              |                                       |
| **CRL Extension** |  **Required**   | **Critical** | **Value**                             |
| CRL Number  | Mandatory | False | Monotonically increasing integer (never repeated) |
| Authority Key Identifier   | Mandatory | False | Octet String: Derived using the SHA-1 hash of the Issuer’s public key in accordance with RFC 5280.  Must match SKI of issuing CA Certificate |
|               |                 |              |                                       |
| **CRL Entry Extension** |  **Required**   | **Critical** | **Value**  
| Reason Code  | Mandatory | False |  Must be included when reason code = key compromise or CA compromise |
| Hold Instruction   |  |  | Not present. |
| Issuing Distribution Point  |  |  | Not present. |
