# French Supermarket Refrigeration Controller Incident

**Research date:** 15 October 2026  
**Domain:** Operational Technology (OT), remote management, incident response

## Executive summary

CERT-FR reported numerous compromises involving remote refrigeration controllers used in French supermarket environments. The affected product families included Danfoss AK-SC and AK-SM, Copeland XWEB, and Dixell XWEB.

News reporting described temperature changes, food spoilage, and business disruption.

## Confirmed

- CERT-FR published an alert on 12 October and updated it on 13 October 2026.
- The advisory identifies the affected product families.
- CERT-FR warns against exposing management interfaces directly to the internet.
- The advisory recommends reducing exposure, using protected access, reviewing configuration, and applying vendor-recommended security measures.

## Unknown or not established by the public advisory

- The exact initial access method for every affected site.
- Whether all compromises used the same technical mechanism.
- Whether one specific vulnerability caused every incident.
- Complete attacker attribution and intent.

## Files

- [Timeline](timeline.md)
- [Technical analysis](technical-analysis.md)
- [Attack-chain model](attack-chain.md)
- [Prevention](prevention.md)
- [Sources](sources.md)
- [Media register](media/README.md)

## Research standard

This case study distinguishes confirmed facts from hypotheses. Do not label a proposed attack path as confirmed unless reliable evidence supports it.
