# Awesome SOC
A collection of sources of documentation, and field best practices, to build/run a SOC.

Those are my view, based on my own experience as SOC/CERT analyst and team manager, as well as well-known papers. Focus is more on SOC than on CERT.

NB: Generally speaking, SOC here refers to detection activity, and CERT/CSIRT to incident response activity.

# TOC
* [Must read](https://github.com/cyb3rxp/awesome-soc/blob/main/README.md#must-read)
* [Fundamental concepts](https://github.com/cyb3rxp/awesome-soc/blob/main/soc_basics.md)
* [Mission-critical means (tools/sensors)](https://github.com/cyb3rxp/awesome-soc/blob/main/README.md#critical-means-toolssensors)
* [SOAR](https://github.com/cyb3rxp/awesome-soc/blob/main/README.md#soar)
* [IT/security Watch (recommended sources)](https://github.com/cyb3rxp/awesome-soc/blob/main/README.md#itsecurity-watch)
* [Detection engineering management](https://github.com/cyb3rxp/awesome-soc/blob/main/detection_engineering.md)
* [Management](https://github.com/cyb3rxp/awesome-soc/blob/main/README.md#management)
* [HR and training](https://github.com/cyb3rxp/awesome-soc/blob/main/README.md#hr-and-training)
* [IT achitecture](https://github.com/cyb3rxp/awesome-soc/blob/main/README.md#it-achitecture)
* [To go further (next steps)](https://github.com/cyb3rxp/awesome-soc/blob/main/README.md#to-go-further)
* [Appendix](https://github.com/cyb3rxp/awesome-soc/blob/main/README.md#appendix)

# Must read

## For a SOC:
* LetsDefend [SOC analyst interview questions](https://github.com/LetsDefend/SOC-Interview-Questions)
* NIST, [Cybersecurity framework](https://www.nist.gov/cyberframework) 
* FIRST, [Building a SOC](https://www.first.org/resources/guides/Factsheet_Building_a_SOC_start_small.pdf) 
* MITRE, [11 strategies for a world-class SOC](https://www.mitre.org/publications/technical-papers/11-strategies-world-class-cybersecurity-operations-center), part 0 (Fundamentals) 


## For a CERT: 
* FIRST, [CERT-in-a-box](https://www.first.org/resources/guides/cert-in-a-box.zip) 
* ENISA, [Good practice for incident management](https://www.enisa.europa.eu/publications/good-practice-guide-for-incident-management)
* NIST, [SP800-86, integration forensics techniques into IR](https://nvlpubs.nist.gov/nistpubs/legacy/sp/nistspecialpublication800-86.pdf) 

## Globally (SOC and CERT):
* CIS, [8 critical security controls](https://www.cisecurity.org/controls/cis-controls-list)
* NIST, [SP800-61 rev2, incident handling guide](https://csrc.nist.gov/publications/detail/sp/800-61/rev-2/final) 
* MITRE, [ATT&CK: Getting started](https://attack.mitre.org/resources/getting-started/)
* ThreatConnect, [SIRP / SOA / TIP benefits](https://threatconnect.com/blog/realizing-the-benefits-of-security-orchestration-automation-and-response-soar/)
* Gartner, [Market Guide for Security Orchestration, Automation and Response Solutions](https://www.gartner.com/doc/reprints?id=1-2ADE1K2G&ct=220621&st=sb) 
* Orange Cyberdefense, [Feedback regarding experience with SOAR in 2020 (in French)](https://www.orangecyberdefense.com/fr/insights/blog/threat-management/soar-quelles-conclusions-en-2020) 
* [Playbook for ransomware incident response (in French)](https://github.com/soufianetahiri/ransomware_Incident_Response_FR)
* FIRST, [CVSS v3.1 specs](https://www.first.org/cvss/specification-document) 
* OASIS Open, [STIX](https://oasis-open.github.io/cti-documentation/stix/intro.html)
* FIRST, [TLP](https://www.first.org/tlp/) (intelligence sharing and confidentiality)


# Fundamental concepts:

## Concepts, tools, missions, attack lifecycle, red/blue/purple teams:
See: [SOC/CSIRT Basic and fundamental concepts](https://github.com/cyb3rxp/awesome-soc/blob/main/soc_basics.md).

## SOC and CISRT core: architecture of detection:
As per [CYRAIL's paper](https://slideplayer.com/slide/15779727/) here is an example of architecture of detection (SIEM, SIRP, TIP ):
![image](https://user-images.githubusercontent.com/16035152/187097659-a1006466-22a5-4c89-b0f1-ace64f54834f.png)




# Critical means (tools/sensors)

## Critical tools for a SOC/CERT:
* **[SIEM](https://www.gartner.com/en/information-technology/glossary/security-information-and-event-management-siem)**:
   * See [Gartner magic quadrant](https://www.bankinfosecurity.com/whitepapers/2021-gartner-magic-quadrant-for-security-information-event-w-8758) 
   * My recommendations: [Splunk](www.splunk.com), [Elastic](https://www.elastic.co/)
* **[SIRP](https://d3security.com/blog/whats-the-difference-between-soar-and-sao/)**:
  * e.g.: [IBM Resilient](https://www.ibm.com/qradar/security-qradar-soar?utm_content=SRCWW&p1=Search&p4=43700068028974608&p5=e&gclid=Cj0KCQjw9ZGYBhCEARIsAEUXITW2yUqAfNqWNeYXyENeUAoqLxV543LT0n2oYhYxEQ47Yjm7NfYTFHAaAtwpEALw_wcB&gclsrc=aw.ds),  [TheHive](https://thehive-project.org/), [SwimLane](https://swimlane.com/)
* **[SOA](https://d3security.com/blog/whats-the-difference-between-soar-and-sao/)**:
  * My recommendations: [IBM Resilient]( https://www.ibm.com/qradar/security-qradar-soar?utm_content=SRCWW&p1=Search&p4=43700068028974608&p5=e&gclid=Cj0KCQjw9ZGYBhCEARIsAEUXITW2yUqAfNqWNeYXyENeUAoqLxV543LT0n2oYhYxEQ47Yjm7NfYTFHAaAtwpEALw_wcB&gclsrc=aw.ds), [SwimLane](https://swimlane.com/), [TheHive](https://thehive-project.org/), [PAN Cortex XSOAR](https://www.paloaltonetworks.com/cortex/cortex-xsoar)
* **[TIP](https://www.ssi.gouv.fr/en/actualite/opencti-the-open-source-solution-for-processing-and-sharing-threat-intelligence-knowledge/)**:
  * My recommendations: [MISP](https://www.misp-project.org/), [OpenCTI](https://www.filigran.io/en/products/opencti/), [Sekoia.io](https://www.sekoia.io/fr/produire-et-personnaliser-votre-propre-intelligence/), [ThreatQuotient](https://www.threatq.com/)
  * don't forget the needed feeds (community / paid ones)
     * My recommendations for paid ones: [ESET](https://www.eset.com/us/business/services/threat-intelligence/), [Sekoia.io](https://www.sekoia.io/fr/sekoia-io-cti/), [Mandiant](https://www.mandiant.com/advantage/threat-intelligence/subscribe), [RecordedFuture](https://www.recordedfuture.com/platform/threat-intelligence)...
     * My recommendations for community ones: MISP default feeds list, [ISAC](https://www.enisa.europa.eu/publications/information-sharing-and-analysis-center-isacs-cooperative-models), [OTX](https://otx.alienvault.com/api), the [Covert.io list](http://www.covert.io/threat-intelligence/).
     

## Critical sensors for a SOC:

* **Antimalware**:
  * See [Gartner magic quadrant](https://www.threatscape.com/microsoft-security-named-leader-in-4-gartner-magic-quadrants/) 
  * My recommendations: [Microsoft Defender](https://docs.microsoft.com/en-us/microsoft-365/security/defender-endpoint/microsoft-defender-antivirus-windows?view=o365-worldwide), [BitDefender](https://www.bitdefender.fr/business/products/workstation-security.html), [ESET Nod32](https://www.eset.com/int/business/solutions/learn-more-about-endpoint-protection/).
* **[Endpoint Detection and Response](https://www.gartner.com/reviews/market/endpoint-detection-and-response-solutions)**:
  * See [Gartner magic quadrant](https://www.microsoft.com/security/blog/uploads/securityprod/2022/01/Gartner-EIA-1963x2048.png) 
  * My recommendations: [SentinelOne](https://www.sentinelone.com/blog/active-edr-feature-spotlight/), [Microsoft Defender for Endpoint](https://docs.microsoft.com/en-us/microsoft-365/security/defender-endpoint/microsoft-defender-endpoint?view=o365-worldwide), [Harfanglab](https://www.harfanglab.io/en/block-cyberattacks).
* **[Secure Email Gateway](https://www.gartner.com/reviews/market/email-security)** (SEG):
  * See [Gartner reviews and ratings](https://www.gartner.com/reviews/market/email-security)
  * My recommendations: [Microsoft Defender for Office365](https://www.microsoft.com/en-us/security/business/siem-and-xdr/microsoft-defender-office-365), [ProofPoint](https://www.proofpoint.com/fr/threat-reference/email-gateway), [Mimecast](https://www.mimecast.com/products/email-security/secure-email-gateway/)
* **[Secure Web Gateway](https://www.gartner.com/en/information-technology/glossary/secure-web-gateway)** (SWG) / Security Service Edge:
  * see [Gartner magic quadrant](https://www.zscaler.fr/cdn-cgi/image/format%3Dauto/sites/default/files/images/page/gartner-magic-quadrant-security-service-edge-sse-2022/zscaler-gartner-sse-2022-%401x.png) 
  * My recommendations: BlueCoat, CISCO, Zscaler, [Netskope](https://www.netskope.com/security-defined/what-is-casb).
* **AD security** (audit logs, or specific security monitoring solutions):
  * My recommendations: [Semperis](https://www.purple-knight.com/fr/?utm_source=gads&utm_medium=paidsearch&utm_campaign=pk_emea&gclid=Cj0KCQjw9ZGYBhCEARIsAEUXITV3yX7Nn6_GR-YVwiOANFvS9wsEQdTyUGHvMMirMzNQEoQ1Q3EQYIMaAjTgEALw_wcB) or [PingCastle](https://www.pingcastle.com/download/)
* **ASM**: Asset Security Monitoring / Attack Surface Management:
  * My recommendations: [Intrinsec (in French)](https://www.intrinsec.com/monitoring-cyber/), [Mandiant](https://www.mandiant.fr/advantage/attack-surface-management)
* **CASB**: [Cloud Access Security Broker](https://www.gartner.com/en/information-technology/glossary/cloud-access-security-brokers-casbs), if company's IT environment uses a lot of external services like SaaS/IaaS:
   * See [Gartner magic quadrant](https://www.netskope.com/wp-content/uploads/2021/01/Screen-Shot-2021-01-05-at-10.15.23-AM-1024x456.png)
   * My recommendations: [Microsoft MCAS](https://www.microsoft.com/en-us/security/business/siem-and-xdr/microsoft-defender-cloud-apps), [Zscaler](https://info.zscaler.com/resources-white-papers-data-protection-challenges?_bt=534426399999&_bk=%2Bzscaler%20%2Bcasb&_bm=b&_bn=g&_bg=121807608181&utm_source=google&utm_medium=cpc&utm_campaign=google-ads-na&gclid=CjwKCAjwu5yYBhAjEiwAKXk_eKLlKaMfJ-oGYItPTHguAmCA_b9WP0zNZgLPqGKjfC19IGmQFFG_9RoCgJAQAvD_BwE), [Netskope](https://www.netskope.com/security-defined/what-is-casb).
 * Deceptive technology:
    * My recomendation: implement [AD decoy acounts](https://medium.com/securonix-tech-blog/detecting-ldap-enumeration-and-bloodhound-s-sharphound-collector-using-active-directory-decoys-dfc840f2f644)
   

## Critical tools for CERT:
* on-demand volatile data collection tool:
  * my recommendations: [VARC](https://github.com/cado-security/varc), [DFIR-ORC](https://github.com/dfir-orc), [FireEye Redline](https://fireeye.market/apps/211364)
* On-demand sandbox:
  * My recommendations: [Joe's sandbox](https://www.joesandbox.com/#windows), [Hybrid Analysis](https://www.hybrid-analysis.com/), etc.
* Forensics and reverse-engineering tools suite:
  * My recommendations: [SIFT Workstation](https://www.sans.org/tools/sift-workstation/), or [Tsurugi](https://tsurugi-linux.org/)
  * My recommendation for reverse engineering, [FireEye Flare-VM](https://github.com/mandiant/flare-vm)
* Incident tracker: 
  * My recommendation: [Timesketch](https://timesketch.org/)
* Scanners:
  * IOC scanners:
    * My recommendations: [Loki](https://github.com/Neo23x0/Loki), [DFIR-ORC](https://github.com/dfir-orc)
  * Offline antimalware scanners: 
    * My recommendation: [Windows Defender Offline](https://support.microsoft.com/en-us/windows/help-protect-my-pc-with-microsoft-defender-offline-9306d528-64bf-4668-5b80-ff533f183d6c)

## Other critical tools for a SOC and a CERT:
* Ticketing system:
  * My recommendation: [GitLab](https://about.gitlab.com/handbook/engineering/security/security-operations/sirt/sec-incident-response.html)
* Knowledge sharing and management tool:
  * My recommendations: [Microsoft SharePoint](https://www.microsoft.com/en-us/microsoft-365/sharepoint/collaboration), Wiki (choose the one you prefer, or [use GitLab as a Wiki](https://docs.gitlab.com/ee/user/project/wiki/)).


# SOAR

## What is SOAR?

As per [Gartner definition](https://securityboulevard.com/2021/08/gartner-soar-magic-quadrant-when-where-and-how/):

![image](https://user-images.githubusercontent.com/16035152/186781422-ebb3996a-da66-4d27-a55f-6065fa84fca5.png)

Hence 3 critical tools (see below): SIRP, TIP, SOA, on top of SIEM.

And in my view, SOAR is more an approach, a vision, based on technology and processes, than a technology or tool per say. 


## Simple and commonly needed automation tools:

* Online automated Hash checker:
  * my recommendation: [Munin](https://github.com/Neo23x0/munin), or with PowerShell [Posh-VT](https://github.com/darkoperator/Posh-VirusTotal)

* Online automated sample analyzer:
  * my recommendation: [malwoverview](https://github.com/alexandreborges/malwoverview)

* (pure) Windows tasks automation:
  * My recommendation: [AutoIT](https://www.autoitscript.com/site/)

* SaaS-based (and partly free, for basic stuff) SOA:
  * [Shuffle](https://shuffler.io/)

## Common automations:

### My recommendations for detection (alerts handling)

Try to implement at least the following automations, leveraging the SOA/SIRP/TIP/SIEM capabilities:
* Make sure all the context from any alert is being automatically transfered to the SIRP ticket, with a link to the SIEM alert(s) in case of.
  * Leverage API (through SOA) if needed to retrieve the missing context info, when using built-in integrations.
* Automatically query the TIP for any artefacts or even IOC that is associated to a SIRP ticket.
* Automatically retrieve the history of antimalware detections for an user and/or endpoint, that is associated to a SIRP ticket.
* Automatically retrieve the history of SIEM detections for an user and/or endpoint, that is associated to a SIRP ticket.
* Automatically retrieve the history of SIRP tickets for an user and/or endpoint, that is associated to a new SIRP ticket.
* Automatically query AD or the assets management solution, for artefact anrichment (user, endpoint, IP, application, etc.).

### My recommendations for reaction (incident response, containment/eradication steps)
* Block an IP on all firewalls (including VPN), and SWG.
* Block an URL on SWG. 
* Block an email address (sender) on SEG.
* Block an exe file (by hash) on endpoints (leveraging EDR, Sysmon, or AppLocker).
* Reset an AD account password.
* Disable an AD account (both user and computer, since computer account disabling will block authentication with any AD account on the endpoint, thus preventing from lateral movement or priv escalation).
* Report a (undetected) sample to security vendors, via email.



# IT/security Watch

* SIEM rules publications:
  * [Sigma HQ (detection rules)](https://github.com/SigmaHQ/sigma/tree/master/rules) 
  * [Splunk Security content (free detection rules for Splunk)](https://research.splunk.com/) 
  * [Michel De Crevoisier's Git](https://github.com/mdecrevoisier/SIGMA-detection-rules)
* Threat intel sources:
  * [Awesome Threat Intelligence](https://github.com/hslatman/awesome-threat-intelligence) 
* Known exploited vulnerabilities: 
  * [CISA catalog](https://www.cisa.gov/known-exploited-vulnerabilities-catalog)
* LinkedIn / Twitter:
  * e.g.: [LinkedIn Information Security Community group](https://www.linkedin.com/groups/38412/) 
* RSS reader/portal:
  * e.g.: [Netvibes](https://www.netvibes.com/phvialle?page=phvialle#Security)  
* Government CERT, industry sector related CERT...
  * e.g.: [CERT-FR](https://www.cert.ssi.gouv.fr/avis/), [CERT-US](https://www.cisa.gov/uscert/ncas/alerts)
* Other interesting websites:
  * e.g.: [ISC](https://isc.sans.edu/), [ENISA](https://www.enisa.europa.eu/publications), [ThreatPost](https://threatpost.com/) ...


# Management

## SOC organization:
* No real need for tiering (L1/L2/L3)
  * this is an old model for service provider, not necesseraly for a SOC!
  * as per MITRE paper (p65):
  >In this book, the constructs of “tier 1” and “tier 2+” are sometimes used to describe analysts
who are primarily responsible for front-line alert triage and in-depth investigation/analysis/
response, respectively. However, not all SOCs are arranged in this manner. In fact, some
readers of this book are probably very turned off by the idea of tiering at all [38]. Some
industry experts have outright called tier 1 as “dead” [39]. Once again, every SOC is different,
and practitioners can sometimes be divided on the best way to structure operations. SOCs
which do not organize in tiers may opt for an organizational structure more based on function.
Many SOCs that have more than a dozen analysts find it necessary and appropriate to tier
analysis in response to these goals and operational demands. Others do not and yet still
succeed, both in terms of tradecraft maturity and repeatability in operations. Either arrangement
can succeed if by observing the following tips that foreshadow a longer conversation about
finding and nurturing staff in “Strategy 4: Hire AND Grow Quality Staff.”

  > Highly effective SOCs enable their staff to reach outside their assigned
duties on a routine basis, regardless of whether they use “tier” to
describe their structure.

* 3 different teams should be needed:
  * security monitoring team (which does actually the "job" of detecting security incident being fully autonomous)
  * security monitoring engineering team (which fixes/improves security monitoring like SIEM rules and SOA playbooks, generates reportings)
  * build / project management team (which does tools integration, SIEM data ingestion, specific DevOps tasks, project management).

## CERT organization:
* Designate among team analysts: 
  * triage officer;
  * incident handler;
  * incident manager;
  * deputy CERT manager.
* Generally speaking, follow best practices as described in ENISA's paper ("Good practice for incident management", see ["Must read"](https://github.com/cyb3rxp/awesome-soc/blob/main/README.md#for-a-cert))

## TTP (attack methods) knowledge base reference:
* Use [MITRE ATT&CK](https://attack.mitre.org/matrices/enterprise/)
* Document all detections (SIEM Rules, etc.) using MITRE ATT&CK ID, whenever possible.

## Data quality and management:
* Implement an information model, like the [Splunk CIM one](https://docs.splunk.com/Documentation/CIM/5.0.1/User/Overview):
  * do not hesitate to extend it, depending on your needs
  * make sure this datamodel is being implemented in the SIEM, SIRP, SOA and even TIP.

## Key documents for a SOC:
* Document an audit policy, that is tailored of the detection needs/expectations of the SOC:
  * The document aims to answer a generic question: what to audit/log, on which equipments/OSes/services/apps?
  * Take the (Yamato Security work)(https://github.com/Yamato-Security/EnableWindowsLogSettings#smbclient-security-log-2-sigma-rules) as an exemple regarding an audit policy required for the Sigma community rules.
* Document a detection strategy, tailored to the needs and expectations regarding the SOC capabilities.
  * The document will aim to list the detection rules (SIEM searches, for instance), with key examples of results, and an overview of handling procedures.


## Detection quality controls: 
 * **Run regular [purpleteaming sessions](https://about.gitlab.com/handbook/engineering/security/threat-management/red-team/purple-teaming/)** in time!!
   * e.g.: [Intrinsec](https://www.intrinsec.com/purple-team/), [FireEye](https://www.fireeye.fr/content/dam/fireeye-www/regional/fr_FR/services/pdfs/ds-purple-team-assessment.pdf)
   * To do it on your own, recommended tool: [Atomic Red Team](https://github.com/redcanaryco/atomic-red-team)
 * Picture the currently confirmed detection capabilities thanks to purpleteaming, with tools based on ATT&CK:
   * e.g.: [Vectr](https://github.com/securityriskadvisors/vectr)


## Detection capabilities representation standard:
*	Use [Security Stack Mappings](https://github.com/center-for-threat-informed-defense/security-stack-mappings) to picture detection capabilities for a given security solution/environment (like AWS, Azure, NDR, etc.): 

## SOC detection capabilities **simplified** representation:
 * Generate [ATT&CK heatmaps](https://www.signalblur.io/getting-started-with-mitres-att-ck-navigator/), to picture the SOC detection capabilities

## SOC Self-assessment:
*	Read the [SOC Cyber maturity model](https://www.soc-cmm.com/introduction/) from CMM
*	Run the [SOC-CMM self-assessment tool](https://www.soc-cmm.com/downloads/latest/) 

## CERT/CSIRT self-assessment:
* Read the [OpenCSIRT cybersecurity maturity framework](https://www.enisa.europa.eu/topics/csirts-in-europe/csirt-capabilities/csirt-maturity/) from ENISA 
  * Run the OpenCSIRT, [SIM3 self-assessment](https://sim3-check.opencsirt.org/#/v1/) 
* Read the [SOC-CMM 4CERT](https://www.soc-cmm.com/4CERT/) from CMM
  * Run the [SOC-CMM 4CERT self-assessment tool](https://www.soc-cmm.com/downloads/latest/soc-cmm%20for%20CERT%201.0%20-%20advanced.xlsx)
  
## Reporting:
* Generate metrics, leveraging the SIRP capabilities to do so:
  * top security incident types
  * top applications associated to alerts (detections)
  * top detection rules triggering most false positives
  * top detection rules taking the longest to be handled
  * number of false positives
  * top 10 SIEM searches (detection rules) triggering false positives
  * number of new detection use-cases being put in production.
  * number of detection rules which detection capability and handling process have been confirmed with purpleteaming session, so far
  * most seen TTP in detection
  * most common incident types
  * mean time to triage (assign) the alerts
  * mean time to handle (verify and be ready for incident response) the alerts  
  * top 10 longest tickets before closure
  * percentage of SIEM data that is not associated to SIEM searches (detection rules)
  
Recommended timeframes to compute those KPI: 1 week, 1 month, and 6 months.

# HR and training

## Recommended SOC trainings:

### Regular trainings:
* [LetsDefend](https://letsdefend.io/)
* [SOC Vel](https://socvel.com/challenges/)
* [ENISA trainings](https://www.enisa.europa.eu/topics/trainings-for-cybersecurity-specialists/online-training-material)
* [Splunk attack range](https://github.com/splunk/attack_range_cloud)


### Certifications:
* [BlueTeamLabs](https://securityblue.team/why-btl1/) (level 1 & 2)
* [SANS 555: SIEM with tactical analytics](https://www.sans.org/cyber-security-courses/siem-with-tactical-analytics/)
* [SANS SEC450: Blue Team Fundamentals: Security Operations and Analysis](https://www.sans.org/cyber-security-courses/blue-team-fundamentals-security-operations-analysis/)
* [OSDA SOC-200](https://www.offensive-security.com/soc200-osda/)
* [SOC & SIEM Security program: L1, L2, L3](https://ethicalhackersacademy.com/products/soc-siem-security-training-program?_pos=1&_sid=b1d241af4&_ss=r)
* [Splunk Core User](https://education.splunk.com/single-subject-courses?_ga=2.213139857.446951445.1644415141-362195814.1644415141)
* [Microsoft Cybersecurity Architect](https://docs.microsoft.com/en-us/certifications/cybersecurity-architect-expert/)
* [AWS Security Fundamentals](https://aws.amazon.com/training/digital/aws-security-fundamentals/?nc1=h_ls)
* [CEH](https://www.eccouncil.org/programs/certified-ethical-hacker-ceh/)


## Recommended CERT/CSIRT trainings:

### Regular trainings:
* [ENISA trainings](https://www.enisa.europa.eu/topics/trainings-for-cybersecurity-specialists/online-training-material)
* [FIRST trainings](https://www.first.org/education/trainings)
* [Malware Traffic Analysis](https://www.malware-traffic-analysis.net/)
* [Hack The Box](https://www.hackthebox.com/)

### Certifications:
* [SANS FOR572: Advanced Network Forensics: Threat Hunting, Analysis, and Incident Response](https://www.sans.org/cyber-security-courses/siem-with-tactical-analytics/)
* [Splunk Core User](https://education.splunk.com/single-subject-courses?_ga=2.213139857.446951445.1644415141-362195814.1644415141)
* [GCIH](https://www.giac.org/certifications/certified-incident-handler-gcih/)
* [SANS FOR508: Advanced Incident Response, Threat Hunting, and Digital Forensics](https://www.giac.org/certifications/certified-incident-handler-gcih/)
* [SANS 555: SIEM with tactical analytics](https://www.sans.org/cyber-security-courses/siem-with-tactical-analytics/)


# IT achitecture

## Disconnect SOC from monitored environment
* Implement SOC enclave (with network isolation), as per MITRE paper drawing:
![image](https://user-images.githubusercontent.com/16035152/186420265-4c0275b2-d70e-4fec-936c-712c1c4802a8.png)




# To go further

## Must read:
* MITRE, [11 strategies for a world-class SOC (remaining of PDF)](https://www.mitre.org/publications/technical-papers/11-strategies-world-class-cybersecurity-operations-center) 
* ANSSI (FR), [EBIOS RM methodology](https://www.ssi.gouv.fr/guide/ebios-risk-manager-the-method/)
*	Microsoft, [SOC/IR hierarchy of needs](https://github.com/swannman/ircapabilities) 
* CISA, [Cyber Defense Incident Responder role](https://www.cisa.gov/cyber-defense-incident-responder)
* Betaalvereniging, [TaHiTI (threat hunting methodology)](https://www.betaalvereniging.nl/wp-content/uploads/TaHiTI-Threat-Hunting-Methodology-whitepaper.pdf) 
* GMU, [Improving Social Maturity of Cybersecurity Incident Response Teams](https://edu.anarcho-copy.org/Against%20Security%20-%20Self%20Security/GMU_Cybersecurity_Incident_Response_Team_social_maturity_handbook.pdf)
* FireEye, [Purple Team Assessment](https://www.fireeye.fr/content/dam/fireeye-www/regional/fr_FR/services/pdfs/ds-purple-team-assessment.pdf)
*	FireEye, [OpenIOC format](https://github.com/fireeye/OpenIOC_1.1/blob/master/IOC_Terms_Defs.md)
*	Kaspersky, [AV / EP / EPP / EDR / XDR](https://usa.kaspersky.com/blog/introducing-kedr-optimum/27062/?reseller=usa_regular-sm_acq_ona_smm__onl_b2c_lii_post_sm-team______&utm_source=linkedin&utm_medium=social&utm_campaign=us_regular-sm_en0177&utm_content=sm-post&utm_term=us_linkedin_organic_pmgk1776sk4g1qp)



## Nice to read:
* NIST, [SP800-53 rev5 (Security and Privacy Controls for Information Systems and Organizations)](https://csrc.nist.gov/publications/detail/sp/800-53/rev-5/final)
* Amazon,	[AWS Security Fundamentals](https://aws.amazon.com/fr/training/digital/aws-security-fundamentals/)   
* Microsoft, [PAW Microsoft](https://docs.microsoft.com/en-us/security/compass/privileged-access-devices) 
* CIS, [Business Impact Assessment](https://bia.cisecurity.org/) 
* Abdessabour Boukari, [RACI template (in French)](https://github.com/cyberabdou/SOC/blob/77f01ba82c22cb11028cde4a862ae0bea4258378/SOC%20RACI.xlsx) 
* Trellix, [XDR Gartner market guide](https://www.trellix.com/fr-fr/solutions/gartner-report-market-guide-xdr.html)
* Elastic, [BEATS agents](https://www.elastic.co/beats/)
* [V1D1AN's Drawing: architecture of detection](https://github.com/V1D1AN/S1EM/wiki/Architecture-guide#the-architecture-of-detection),
* [RFC2350](https://www.cert.ssi.gouv.fr/uploads/CERT-FR_RFC2350_EN.pdf) (CERT description)
* [Awesome Security Resources](https://github.com/Johnson90512/Awesome-Security-Resources)
* [Incident Response & Computer Forensics, 3rd ed](https://www.google.fr/books/edition/Incident_Response_Computer_Forensics_Thi/LuWINQEACAAJ?hl=fr)
* [GDPR cybersecurity implications (in French)](https://atelier-rgpd.cnil.fr/) 
* [SANS SOC survey 2022](https://www.splunk.com/en_us/pdfs/resources/whitepaper/sans-soc-survey-2022.pdf)


## SOC sensors, nice to have:
* Honeypot:
  * My recommendation: [Canary.tools](https://canary.tools/)
* NDR:
  * My recommendation: [Gatewatcher](https://www.gatewatcher.com/en/our-solutions/trackwatch/)
* MDM:
  * My recommendation: [Microsoft Intune](https://docs.microsoft.com/en-us/mem/intune/fundamentals/what-is-intune)
* DLP:
  * See [Gartner reviews and ratings](https://www.gartner.com/reviews/market/data-loss-prevention)
* Network TAP:
  * My recommendation: [Gigamon](https://www.gigamon.com/products/access-traffic/network-taps.html)


## Management:
* **Define SOC priorities, with feared events and offensive scenarios (TTP) to be monitored**, as per risk analysis results.
  * My recommendation: leverage EBIOS RM methodology (see [above](https://github.com/cyb3rxp/awesome-soc/blob/main/README.md#to-go-further)).

* Leverage machine learning, wherever it can be relevant in terms of good ratio false positives / real positives.
  * My recommendation: be careful, try not to saturate SOC consoles with FP.

* Make sure to **follow the 11 strategies for a (world class) SOC**, as per MITRE paper (see [Must Read](https://github.com/cyb3rxp/awesome-soc/blob/main/README.md#must-read)).

* Publish your RFC2350, declaring what your CERT is (see "Nice to read" [above](https://github.com/cyb3rxp/awesome-soc/blob/main/README.md#to-go-further))


## Harden SOC environment
* Implement hardening measures on SOC workstations, servers, and IT services that are used (if possible).
   * e.g.: [CIS](https://www.cisecurity.org/), [Microsoft Security Compliance Toolkit](https://www.microsoft.com/en-us/download/details.aspx?id=55319)
* Put the SOC assets in a separate AD forest, as [forest is the AD security boundary](https://docs.microsoft.com/en-us/windows/security/threat-protection/windows-firewall/gathering-information-about-your-active-directory-deployment), for isolation purposes, in case of a global enterprise's IT compromise
* Create/provide a disaster recovery plan for the SOC assets and resources.


# Appendix

## License:
[CC-BY-SA](https://en.wikipedia.org/wiki/Creative_Commons_license)

## Special thanks:
Yann F., Wojtek S., Nicolas R., Clément G., Alexandre C., Jean B., Frédérique B., Pierre d'H., Julien C., Hamdi C., Fabien L., Michel de C., Gilles B., Olivier R., Jean-François L., Fabrice M., Pascal R., Florian S., Maxime P., Pascal L., Jérémy d'A., Olivier C. x2, David G., Guillaume D., Patrick C., Lesley K., Gérald G., Jean-Baptiste V., Antoine C. ...
