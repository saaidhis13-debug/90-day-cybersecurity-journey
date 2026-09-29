# Day 15 of 90: Phishing Analysis Project (Capstone)

- **Challenge:** Completed my first end-to-end security project analyzing a live phishing website and mapping its infrastructure.
- **My Focus:** Extracted Indicators of Compromise (IOCs), inspected sender IP data, traced malicious URLs, and analyzed TLS certificate metadata.
- **Key Takeaway:** Moving from passive learning to active artifact analysis—documenting structural telemetry like a threat analyst.
- **Analyst Report:**

```text
============================================================
 PHISHING EMAIL ANALYSIS REPORT
============================================================

Analyst:        Saaidh Solih
Analysis Date:  29/09/2026
Engagement:     Suspected Phishing Email Triage
Methodology:    Headers > Sender > Content > Links > Verdict


------------------------------------------------------------
 1. EMAIL METADATA
------------------------------------------------------------

Subject:        Interbank Notification
From (display): Interbank Alert
From (actual):  admin@bienvenidointeber.site
Reply-To:       admin@bienvenidointeber.site
Date received:  29/09/2026
Recipient:      analyst@local.test


------------------------------------------------------------
 2. EXECUTIVE SUMMARY
------------------------------------------------------------

Email confirmed as phishing. The sender domain 
bienvenidointeber.site is a suspicious registration 
hosting a credential-harvesting landing page. The embedded 
link redirects to a fraudulent page designed to capture 
sensitive banking user data.


------------------------------------------------------------
 3. HEADER ANALYSIS
------------------------------------------------------------

SPF:            FAIL — sender IP not authorised for the claimed domain
DKIM:           NONE — no signature present
DMARC:          FAIL — alignment failed

Originating IP: 66.29.148.182
IP Geolocation: United States (NAMECHEAP-NET)
Reverse DNS:    Checked via Namecheap infrastructure


------------------------------------------------------------
 4. SENDER DOMAIN ANALYSIS
------------------------------------------------------------

Domain:           bienvenidointeber.site
Registered on:    September 2026
Registrar:        Namecheap, Inc., US
Privacy enabled:  Yes
Domain age:       Very recent (Newly Registered Domain)
Lookalike of:     Target financial institution


------------------------------------------------------------
 5. CONTENT INDICATORS
------------------------------------------------------------

  [x] Urgency: Account alert / redirection notice
  [x] Generic greeting: Standardized template
  [x] Authority impersonation: Claims to be an Interbank service
  [x] Malicious redirection link


------------------------------------------------------------
 6. LINK ANALYSIS
------------------------------------------------------------

Visible link text:  "Click here to verify your account"
Actual URL:         [http://www.bienvenidointeber.site](http://www.bienvenidointeber.site)
Destination domain: bienvenidointeber.site
URL shortener:      No
HTTPS:              Valid (Issued by YR1 on September 24th, 2026)
Landing page:       Phishing website clone


------------------------------------------------------------
 7. VERDICT
------------------------------------------------------------

Classification:   PHISHING
Confidence:       HIGH
Severity:         HIGH

Reasoning: The email redirects users to a newly registered 
domain hosted on Namecheap infrastructure with a recently 
generated TLS certificate, matching typical adversary 
infrastructure setup for credential harvesting.


------------------------------------------------------------
 8. RECOMMENDED ACTIONS
------------------------------------------------------------

If you received this email:
  [x] Do not click any links
  [x] Report to your email provider (mark as phishing)
  [x] Delete after reporting

If you clicked the link:
  [x] Change password on the affected account
  [x] Enable 2FA if not already on
  [x] Check account for unauthorised sessions
  [x] Scan device for malware

============================================================
 END OF REPORT
============================================================
