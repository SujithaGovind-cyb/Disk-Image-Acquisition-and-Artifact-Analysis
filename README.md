# Disk-Image-Acquisition-and-Artifact-Analysis

This repository documents a two-part digital forensic investigation focused on rigorous evidence acquisition and in-depth disk image analysis. Part 1 details the proper acquisition of a digital device (USB flash drive) using command-line tools (dcfldd) and verification via cryptographic hashing. Part 2 involves the systematic analysis of a suspect disk image using Autopsy to uncover malicious activity, focusing on deleted file recovery, registry analysis, and keyword searching. This project highlights adherence to the Chain of Custody and the ability to identify critical forensic artifacts that inform incident response.

### Skills Learned

Forensic Acquisition & Integrity
- Mastering command-line tools (dcfldd) for forensic imaging and ensuring data integrity using cryptographic hashing (SHA-256).

Disk Artifact Analysis
- Conducting in-depth analysis of hard disk images using Autopsy to reconstruct user activity.

Evidence Recovery
- Performing deleted file recovery, keyword analysis, and registry analysis to extract sensitive information (e.g., credentials, communication patterns).

Timeline Reconstruction
- Analyzing metadata and system logs to establish a chronological overview of events.

Threat Identification
- Identifying indicators of compromise (IOCs) such as suspicious executables (Aollad.exe), program execution, and malicious website visits.

### Tools Used

- Forensic Workstation: Kali Linux (for acquisition)
- Acquisition Tool: dcfldd (or dd)
- Forensic Analysis Suite: Autopsy
- Hashing/Integrity: SHA-256

## Steps

The investigation followed a precise, two-stage process to ensure the integrity and thoroughness of the forensic examination:

1. Forensic Image Acquisition (Establishing Chain of Custody)

- Media Preparation: Documented and secured the target USB flash drive, ensuring the physical chain of custody was maintained.
- Command-Line Imaging: Used the dcfldd utility within a Linux environment to create a bit-for-bit forensic image of the physical media.
- Integrity Verification: Calculated the cryptographic hash (SHA-256) of both the original source drive and the newly created image file to mathematically prove the image's integrity. (See Figure 2.2 - Hash Verification Results).
- Documentation: Logged the entire acquisition process, including commands, timestamps, and hash values, to maintain a legal and verifiable record.

2. Disk Artifact Analysis (Autopsy)

- Case Setup: Created a new case in Autopsy and ingested the provided suspect disk image for analysis.
- Keyword Analysis: Executed targeted keyword searches for high-value terms (e.g., "Password," "Domex1") which successfully identified communication patterns and sensitive information.
- Deleted File Recovery: Ran an extensive deleted file analysis, recovering numerous system files and two critical files (signons-1.txt, domex1@atwola[1].txt) containing cookie data and potential email credentials from malicious sources. (See Figure 4.5 - Deleted Credential File Preview).
- Registry & Program Analysis: Performed registry analysis to uncover crucial system data, user account information, and, importantly, the presence of suspicious software (MobileOptionPack) and executables (Aollad.exe, Msiexec.exe) recently run on the system.
- Timeline Reconstruction: Utilized metadata and file system attributes to generate a chronological timeline of user logins, file accesses, and device attachments, helping to reconstruct the sequence of the compromise.

 Ref 1: Security Onion Case Events
