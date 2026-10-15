# Heartbleed: The Memory Leak That Shook Internet Security

**Disclosure date:** 7 April 2014  
**CVE:** CVE-2014-0160  
**Technology:** OpenSSL and TLS/DTLS heartbeat extension

## The people behind the discovery

Heartbleed was independently discovered by Neel Mehta of Google Security and by a Codenomicon team consisting of Riku, Antti, and Matti. Neel Mehta first reported the issue to OpenSSL; Codenomicon also participated in coordinated reporting.

The discovery illustrates how systematic security testing and independent research can uncover serious implementation defects in widely used software.

## The technical failure

TLS heartbeat messages let one endpoint check that the other endpoint is still responsive.

A client could send a payload and claim a length for it. The vulnerable OpenSSL implementation did not properly validate that claimed length against the actual payload.

A crafted request could therefore make the implementation return extra bytes from process memory. One response could expose up to 64 KB. Repeated requests could potentially expose additional memory.

Depending on the contents of memory, sensitive material could include credentials, session information, private keys, or other data. Exposure was possible, not guaranteed in every request.

## Why TLS did not prevent it

TLS protects communication, but Heartbleed exploited a bug inside the software implementing TLS. The attacker did not need to defeat the cryptographic algorithm. The implementation disclosed memory it should never have returned.

## Response and recovery

OpenSSL 1.0.1g fixed the issue. Organizations still needed to identify affected services, deploy the fix, and assess whether exposed secrets needed to be replaced or invalidated.

Depending on exposure, recovery could include replacing private keys, revoking and reissuing certificates, invalidating sessions, and changing credentials. Patching alone could not prove that secrets had never been exposed.

The Heartbleed documentation also notes that exploitation might leave no reliable trace in ordinary logs, making certainty about past exploitation difficult.

## Lessons for security researchers

- Validate all externally controlled length fields.
- Understand the difference between cryptographic strength and implementation security.
- Distinguish possible impact from demonstrated exposure.
- Treat remediation as a process of restoring trust, not merely installing a patch.
- Document the discovery, disclosure, fix, and recovery process.

## Primary sources

- Heartbleed technical FAQ: https://www.heartbleed.com/
- OpenSSL security advisory: https://www.openssl.org/news/secadv/20140407.txt
- Mozilla security response: https://blog.mozilla.org/security/2014/04/08/heartbleed-security-advisory/
