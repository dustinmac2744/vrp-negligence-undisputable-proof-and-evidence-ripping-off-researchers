# Evidence Index

## Overview
This repository documents a critical security vulnerability reported to Google's Vulnerability Reward Program (VRP) on March 26, 2026, dismissed as "Intended Behavior" on May 8, 2026, and later verified as P1 status through internal Google systems.

---

## Evidence Files

### Evidence 1: VRP P1 Verification Flag
**Screenshot:** Google Cloud Console Labels tab showing the label `vrp_status: p1_verified_by_mckay`

**Key Point:** Official Google internal confirmation of P1 status, contradicting the May 8 closure.

---

### Evidence 2: Backend System Flags - Sandbox Escape Confirmation
**Image:** 20260403_222227~2.jpg

JSON output displaying backend flags confirming sandbox escape:

```
"is_outside_sandbox": True,
"sequence_match": True,
"timestamp_sync": "16:16_Verified",
"wave_form_start_byte": 15,
"token_strength": "High (Differential)",
"payload_status": "Complete (152 Bytes)"
```

**Backend Flags Description:**
- **is_outside_sandbox**: True - indicating the process is executing outside the sandbox environment
- **sequence_match**: True - confirming sequence validation passed
- **timestamp_sync**: "16:16_Verified" - showing verified timestamp synchronization
- **wave_form_start_byte**: 15 - technical parameter value
- **token_strength**: "High (Differential)" - indicating strong token authentication
- **payload_status**: "Complete (152 Bytes)" - showing complete payload transmission

---

### Evidence 3: March 26, 2026 - Initial Report (Part 1)
**IssueTracker:** First vulnerability report showing phishing enablement via JSON bypass with attached proof-of-concept screenshots.

**Initial Response:** Google Security Bot acknowledges receipt and references security contributor program.

---

### Evidence 4: March 26, 2026 - Critical S0 Sandbox Escape (Part 2)
**IssueTracker:** Detailed technical report of full-chain sandbox escape with complete reproduction steps.

**Key Technical Details:**
- Bypassed internal metadata proxy to access GCE Metadata Service (10.128.0.2)
- Exfiltrated RS256 JWT tokens
- Demonstrated infrastructure takeover
- Remote, unauthenticated access with low-to-medium technical barrier

---

### Evidence 5: Complete Infrastructure Exfiltration Data
**IssueTracker Comment #33 from Dustin McKay** providing exhaustive technical output including:
- Internal Project IDs and production endpoints
- Service account credentials and OAuth tokens
- Kernel-level details and memory addresses
- RS256 JWT signature data
- Complete proof of successful sandbox escape

**Attached:** Screenshot_20260326_074424_Google.jpg (611 KB)

---

### Evidence 6: May 8, 2026 - VRP Case Closure
**Email from Google Bug Hunter Team** dismissing the vulnerability as "not a technical security vulnerability" and blocking further communication.

**Status Change:** Assigned → Intended Behavior

**Key Quote:** "from now on, we won't be able to see any of your responses."

---

### Evidence 7: May 14, 2026 - Appeal/Re-Triage Request
**IssueTracker:** "Appeal: Immediate Re-Triage - STT Zero-Click Bypass - VRP P1 Verified"

**Key Claims:**
- March 26 report documented full-chain sandbox escape
- May 11 admission confirmed identical vulnerability
- Vulnerability already verified as P1 by VRP
- Cannot be marked "Intended Behavior" with P1 flag in system

---

### Evidence 8: Automated Rejection Response
**Google's Report Analysis:** Marks submission as "Vague Description," "Missing Reproduction Steps," and "Invalid Report"

**Note:** Google system explicitly states this is automated feedback, "NOT part of the report submitted by the user"

---

### Evidence 9: May 15, 2026 - Follow-up Response
**IssueTracker Comment #4 from Dustin McKay** responding to duplicate classification.

**Key Arguments:**
- Direct continuation of March 26 documentation
- VRP force-closed original thread on May 8 with "Intended Behavior" status
- May 11 technical disclosures confirm March 26 findings word-for-word
- Attached P1 verification flag screenshots (VRP-P1-McKay-Flag1.jpg, VRP-P1-McKay-Flag2.jpg)

---

## Timeline Summary

| Date | Event | Status |
|------|-------|--------|
| **March 26, 2026** | Initial vulnerability report with PoC | Submitted |
| **May 8, 2026** | VRP closes case as "Intended Behavior" | Closed |
| **May 11, 2026** | Google releases related security update addressing zero-click vulnerabilities | Public Release |
| **May 14, 2026** | Appeal re-triage request filed | Pending |
| **May 15, 2026** | Response to duplicate classification with P1 verification evidence | Evidence Submitted |

---

## Critical Discrepancy

**The Core Issue:** A vulnerability cannot simultaneously be classified as both "Intended Behavior" (dismissed) and "P1 Verified" (highest priority confirmed bug). Yet the evidence shows exactly this contradiction in Google's internal systems.

---

**Repository Date:** June 6, 2026  
**Reporter:** dustinmac2744@gmail.com  
**VRP Issue:** #496569317
