# Phishing Email Investigation Report

## Findings

**Time:** 2021-01-26 09:41:18 EAT

**Sender:** billjobs@microapple[.]com

**Recipient:** themajoronearth@gmail[.]com

**IOC Domain:** pashter[.]com

**IOC IP:** 93[.]99[.]104[.]210

**Malicious Files:** DaughtersCrown.jpeg, GoodJobMajor.pdf, Money.xlsx

## Investigation

On January 26, 2021, at 09:41:18 EAT, TheMajorOnEarth received a suspicious email from Pestero Negeja demanding 1 billion CoCanDs to release abducted CoCanDians.

Analysis of the email headers revealed an SPF authentication failure and a mismatch between the From and Reply-To addresses, both of which are potential phishing indicators.

Three suspicious files were identified: DaughtersCrown.jpeg, GoodJobMajor.pdf, and Money.xlsx. Initial file reputation checks on VirusTotal returned clean results. However, I continued the investigation by analyzing Sysmon logs to investigate the behavior of the files after execution.

The Sysmon analysis revealed that the files executed malicious commands and made unusual network connections. This provided behavioral evidence that was not identified through the initial file reputation checks.

## Who, What, When, Where, Why, How

**Who:** Pestero Negeja sent the suspicious email.

**What:** A suspicious email containing a ransom demand and malicious files was received.

**When:** January 26, 2021, at 09:41:18 EAT.

**Where:** TheMajorOnEarth's email account.

**Why:** The email attempted to pressure the recipient into making a payment and also involved activity that could lead to system compromise.

**How:** The email contained files that, when executed, were observed through Sysmon to execute malicious commands and make unusual network connections.

## Conclusion

The investigation confirmed that the email contained malicious files. Although the initial VirusTotal checks returned clean results, deeper behavioral analysis using Sysmon revealed malicious command execution and unusual network activity.

This investigation demonstrated the importance of not relying solely on file reputation or static indicators. Endpoint telemetry and behavioral analysis provided additional evidence that helped identify malicious activity.

## Recommendations

* Investigate the identified network connections and IOC domain/IP for additional affected systems.
* Determine whether the malicious files established persistence or performed additional actions.
* Identify the full scope of the activity and any other affected users or systems.

