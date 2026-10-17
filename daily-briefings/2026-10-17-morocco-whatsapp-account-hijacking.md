# WhatsApp Account Hijacking Reports in Morocco: Social Engineering vs. Zero-Click Attacks

**Publication date:** 17 October 2026  
**Category:** Cybersecurity News · Social Engineering · Account Security  
**Geographic relevance:** Morocco  
**Research status:** Public reporting reviewed; exact incident mechanisms remain unverified

## 1. News Report

During 15–16 October 2026, warnings circulated across Moroccan social media about WhatsApp account hijacking. Users reported receiving unexpected verification-code requests, while some reported losing access to their accounts.

Moroccan media outlets covered the concerns and explained how attackers can exploit verification processes and manipulate users into granting access.

Yabiladi published an interview with Moroccan cybersecurity expert Yousra El Haddad explaining how verification-code theft can lead to account takeover. Al3omk reported that the information available at the time did not establish a coordinated, large-scale cyberattack or a newly exploited WhatsApp vulnerability.

**Assessment:** Account-takeover attempts and social-engineering techniques are credible explanations for some reported cases. However, the available public reporting does not establish the total number of victims, a single coordinated campaign, or a confirmed zero-click exploit.

Sources:

- Yabiladi: https://en.yabiladi.com/articles/details/205142/whatsapp-account-losses-reported-morocco.html
- Al3omk: https://al3omk.com/1197255.html
- Al Massae: https://almassae.com/

## 2. Technical Analysis: Three Different Attack Paths

WhatsApp account security involves several distinct mechanisms: phone-number registration, verification, linked-device authorization, and protection of message history.

An attacker may abuse one mechanism without exploiting a software vulnerability.

### 2.1 Verification-Code Theft

A common account-takeover scenario begins when an attacker attempts to register a victim's phone number on another device.

The service sends a verification code to the phone number. The attacker then tries to persuade the victim to disclose that code, potentially by impersonating technical support, a trusted contact, or a legitimate business.

Simplified attack flow:

```text
Attacker
   |
   | Initiates registration using victim's number
   v
WhatsApp requests phone-number verification
   |
   v
Victim receives verification code
   |
   | Attacker uses deception to obtain the code
   v
Attacker submits the code
   |
   v
Account takeover may succeed
```

The critical failure is the disclosure of an authentication factor to an unauthorized party.

Receiving an unexpected code does not itself mean the account has been compromised. It may indicate an attempted registration, and a registration attempt alone does not establish that the attacker succeeded.

WhatsApp's official guidance explicitly warns users never to share verification codes.

Reference: https://faq.whatsapp.com/479314433984258

### 2.2 Fraudulent Linked-Device Authorization

WhatsApp supports linked devices so users can access their accounts from computers and other devices.

Attackers may abuse this legitimate feature through deception. A victim might be persuaded to scan a QR code or complete a device-linking procedure under the false impression that they are verifying, securing, or recovering their account.

Simplified flow:

```text
Attacker prepares a deceptive request
             |
             v
Victim is directed into a linking process
             |
             v
Victim authorizes an attacker-controlled device
             |
             v
An additional session may gain account access
             |
             v
Attacker may impersonate the victim
```

This technique is often described as device-linking fraud or ghost pairing.

The distinction is important: the attacker can abuse a legitimate authorization mechanism without necessarily exploiting a vulnerability in WhatsApp's code.

The existence of this technique does not prove it was used in every reported Moroccan incident.

Further reporting:

https://mobile.telquel.ma/2026/09/11/new-scams-on-whatsapp-how-do-they-work-and-how-can-you-avoid-them_2006684

### 2.3 Genuine Zero-Click Exploitation

A zero-click attack exploits a vulnerability without requiring the victim to deliberately interact with the malicious content.

For example, an automatically processed message or media object could trigger a vulnerability in a susceptible application component.

A simplified hypothetical flow:

```text
Attacker sends crafted content
             |
             v
Application processes content automatically
             |
             v
Vulnerable component mishandles the input
             |
             v
Exploitation may occur
             |
             v
Impact depends on the vulnerability
and the application's security controls
```

Successful exploitation may require multiple vulnerabilities or additional conditions. Automatic processing alone is not enough to prove that exploitation occurred.

A genuine zero-click claim requires technical evidence supporting the vulnerability, exploitation path, and resulting impact.

No such evidence has been established by the public reporting reviewed for this incident.

## 3. Is This a Zero-Click Attack?

The available evidence does not justify classifying the reported Moroccan WhatsApp account takeovers as a confirmed zero-click campaign.

These terms describe different things:

| Concept | Meaning |
|---|---|
| Account takeover | An unauthorized party gains control of an account. |
| Social engineering | An attacker manipulates a person into disclosing information or authorizing an action. |
| Verification-code theft | An attacker obtains a code used in an account-verification process. |
| Device-linking fraud | A victim is tricked into authorizing an additional device or session. |
| Zero-click exploitation | A vulnerability is exploited without requiring deliberate victim interaction with the malicious content. |

A victim may report being hacked without clicking a link. That statement describes their experience, not necessarily the underlying technical mechanism.

Other possibilities include fraudulent device linking, SIM-related compromise, abuse of an existing session, or an exploit that has not yet been identified.

These possibilities should remain hypotheses until evidence distinguishes between them.

## 4. What About Previous Conversations and Photos?

Account takeover does not automatically imply access to all historical messages.

According to WhatsApp's recovery guidance, registering an account on another device does not, by itself, give an attacker access to the previous owner's chat history stored on their phone.

However, a compromised account can still be used to impersonate its owner, contact friends and colleagues, solicit money, and exploit information available through accessible conversations or groups.

Exposure may be greater if the attacker also gains access to a linked device, the victim's phone, or a restorable backup.

Reference: https://faq.whatsapp.com/1131652977717250/

## 5. Defensive Measures

### For individual users

- Never disclose WhatsApp registration codes or account-security credentials.
- Enable two-step verification and configure recovery options.
- Review linked devices and disconnect unfamiliar sessions.
- Never scan a QR code supplied by another person to supposedly secure or verify an account.
- Verify urgent requests for money through an independent communication channel.
- Keep WhatsApp and the device operating system updated.

### If an account has been compromised

1. Re-register the phone number through the official WhatsApp application.
2. Follow the official recovery process if an unfamiliar two-step verification PIN is requested.
3. Warn contacts through another channel that the account may be compromised.
4. Review linked devices after regaining access.
5. Preserve relevant messages and screenshots if reporting the incident.

Official recovery guidance:

https://faq.whatsapp.com/1131652977717250/

### For organizations

Organizations that depend on WhatsApp for customer communication should establish an independent process for verifying financial requests, notifying customers of impersonation incidents, and recovering compromised accounts.

Staff should be trained to distinguish authentication codes from ordinary notifications and to recognize attempts to manipulate device-linking workflows.

## 6. Investigation Questions

The following questions would help establish the technical cause of an individual incident:

1. Did the victim receive an unexpected registration code?
2. Was the code disclosed, or was a device-linking action authorized?
3. Was the victim logged out, or did the account remain active on the primary phone?
4. Were unfamiliar linked devices present?
5. Was there evidence of SIM-related compromise or unauthorized access to the victim's device?
6. Is there forensic evidence of a software vulnerability being exploited?
7. What evidence connects separate reports to the same campaign, if any?

These questions help distinguish observed symptoms from an established attack path.

## 7. Conclusion

The October 2026 reports from Morocco highlight the risks of account impersonation, verification-code theft, and deceptive authorization.

The central lesson is methodological: account takeover is an outcome, while zero-click describes a characteristic of an exploitation path. Neither term proves the other.

Without forensic evidence, classifying these incidents as a confirmed zero-click attack would be premature.

**Research principle: Evidence over assumptions. Mechanisms over headlines. Prevention over speculation.**

## Sources

1. Yabiladi, “WhatsApp account losses reported in Morocco: What causes them and how to stay protected,” 16 October 2026.  
   https://en.yabiladi.com/articles/details/205142/whatsapp-account-losses-reported-morocco.html

2. Al3omk, reporting on the circulating claims of mass WhatsApp account compromises in Morocco, 16 October 2026.  
   https://al3omk.com/1197255.html

3. TelQuel, “New scams on WhatsApp: How do they work? and how can you avoid them?”, 11 September 2026.  
   https://mobile.telquel.ma/2026/09/11/new-scams-on-whatsapp-how-do-they-work-and-how-can-you-avoid-them_2006684

4. WhatsApp Help Center, “Received verification code without requesting it.”  
   https://faq.whatsapp.com/479314433984258

5. WhatsApp Help Center, “How to recover a compromised account.”  
   https://faq.whatsapp.com/1131652977717250/

**Source limitation:** Media reports describe complaints and explain known attack techniques. They do not establish that every reported incident shared the same cause. The exact number of affected users, any common attacker, and any connection to a zero-click vulnerability remain unverified.
