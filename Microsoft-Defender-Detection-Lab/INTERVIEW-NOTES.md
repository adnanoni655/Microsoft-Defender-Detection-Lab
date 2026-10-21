# Recruiter and Interview Notes

## Resume project entry
**Microsoft Defender Antivirus Detection & Remediation Lab**  
*Tools: Microsoft Defender Antivirus, Windows Security, PowerShell*

- Reviewed endpoint protection settings, including real-time protection, cloud-delivered protection, automatic sample submission, and potentially unwanted app blocking.
- Validated antivirus detection with the harmless EICAR test artifact and reviewed the resulting Protection History entry.
- Investigated Defender detection records using PowerShell cmdlets and verified that the test file was absent from its original path.
- Documented the workflow and evidence in a GitHub portfolio repository.

## 60-second interview answer
“I built a hands-on Microsoft Defender Antivirus lab to understand how endpoint protection detects and handles a test artifact. I reviewed the protection settings, checked the quick-scan result, and used the harmless EICAR test file to validate detection. Defender identified it as `Virus:DOS/EICAR_Test_File`. I reviewed Protection History and used PowerShell commands such as `Get-MpThreatDetection` and `Get-MpThreat` to inspect the detection records and action status. I also checked the original file path with `Test-Path`, which returned `False`. I documented the evidence and findings in GitHub. This was a local Defender Antivirus lab, not an enterprise Defender for Endpoint deployment.”

## Common interview questions

**Why EICAR?**  
EICAR is a harmless, standardized antivirus test artifact. It validates antivirus detection without requiring real malware.

**How did you investigate the alert?**  
I reviewed Windows Security Protection History and used `Get-MpThreatDetection` to examine detection timestamps, threat IDs, action-success values, and resources.

**How did you verify the file was gone?**  
`Test-Path "$env:USERPROFILE\Downloads\eicar.com.txt"` returned `False`, so the file was absent from that original path when checked.

**What did the quick scan show?**  
The captured screen showed 0 threats found across 30,331 files scanned. That result only describes that particular scan.

**What would you do next?**  
I would extend the lab by correlating endpoint events with a SIEM such as Splunk or Wazuh and practicing investigation of additional safe, simulated endpoint events.

## Accuracy note
Do not describe this project as real-malware analysis or an enterprise EDR deployment. EICAR is harmless, and this lab used local Microsoft Defender Antivirus.
