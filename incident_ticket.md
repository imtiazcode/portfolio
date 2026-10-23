# Incident Ticket

Meridian Finance Group, its staff and all IP addresses/domains below are entirely
synthetic (addresses are drawn from IANA documentation ranges reserved by
RFC 5737 and RFC 2606).**

| Field | Value |
|---|---|
| Ticket ID | SOC-2026-0914-041 |
| Priority | High |
| Status | Open — assigned for investigation |
| Reported by | Security Information and Event Management (SIEM) — IDS signature alert |
| Date/time raised | 2026-09-14 09:42 |
| Organisation | Meridian Finance Group (fictional) |
| Affected host | FIN-WKS07 (10.1.1.52), Finance department workstation |
| Affected user | M. Alvarez (m.alvarez), Accounts Payable Analyst |

## Summary provided to the SOC analyst

At 09:42 the SOC's IDS raised a "possible C2 beacon / suspicious outbound
HTTP" alert for host FIN-WKS07, triggered by a large outbound HTTP POST to
an external host shortly after a sustained pattern of small, regular HTTP
requests to the same destination. The SOC shift lead has pulled a short
network capture around the affected host (`incident_FIN-WKS07.pcap`,
08:02–10:07), relevant firewall/DNS/proxy logs, host logs from the
endpoint's Sysmon and Windows Security event channels, a memory
acquisition taken from the host shortly after triage began, and the
suspicious executable file recovered from the host.

You have been assigned this ticket as the incident responder. The
following is known so far:

- The user reports receiving what looked like a routine vendor invoice
  email around 08:00 and opening the attached file shortly afterwards.
- No other hosts have yet been confirmed as affected, but discovery-style
  activity (an attempt to enumerate other hosts and an SMB connection to
  the finance file server, 10.1.1.10) was observed from FIN-WKS07.
- The host has not yet been isolated from the network. Finance month-end
  processing is in progress and business stakeholders are asking whether
  the host and the finance file server can continue to be used.

## Questions the SOC manager needs answered

1. What happened, in order, from initial delivery to detection? Provide a
   timeline with evidence references (packet numbers/timestamps, log
   lines, memory artefacts).
2. What is the malware, what type/family characteristics does it show, and
   what is its likely infection life cycle and capability?
3. What hosts, accounts or data may have been affected, and what is your
   assessment of the business impact, including to the finance file
   server?
4. What containment and eradication actions do you recommend, and in what
   order, given that business operations are still running on the
   affected network segment?
5. What indicators of compromise should be distributed to the wider
   environment to check for and block further activity?
6. What ethical, legal or professional issues apply to how this
   investigation and its evidence should be handled?

— SOC Shift Lead
