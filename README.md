# Email Phishing Investigation

## Overview

In this lab, I investigated a phishing email in a controlled Windows environment. I analyzed the email headers, decoded Base64-encoded content, extracted embedded files, and examined file signatures to identify their actual file types.

## Steps I Took

1. **Email Analysis**: Downloaded the email file and opened it using Notepad++ in a controlled Windows lab environment. I then identified the sender's domain and checked its reputation on VirusTotal.

2. **Base64 Decoding of the text:** Used CyberChef to decode Base64-encoded content found in the email.

3. **File Extraction and Identification:** Copied the raw Base64 text into CyberChef and decoded it. I then applied the Hex operation to identify the file's magic number and determine its actual file type. After confirming the file type, I removed the Hex operation in CyberChef. 


4. **File Signature Verification:** Used Gary Kessler's File Signature Analysis resource to identify the actual file type based on its magic number.

5. **File Reconstruction:** After confirming the actual file type, saved the file in its identified format using the appropriate file extension.

6. **Additional File Analysis:** Repeated the file signature identification and reconstruction process for other embedded files.

7. **Metadata Extraction:** Used ExifTool to extract metadata from the files recovered from the email.

8. **File Reputation Check:** Finally, I checked the SHA-256 hashes of the extracted files on VirusTotal. 



## Tools I Used

* **Notepad++** – To inspect the raw email content and headers.
* **CyberChef** – To decode Base64 content and convert data for file signature analysis.
* **HxD** – To inspect hexadecimal data and file signatures.
* **7-Zip** – To extract and inspect archive contents.
* **ExifTool** – To extract file metadata.
* **Gary Kessler's File Signature Database** – To verify file types using their magic numbers.

## Email Header Fields I Analyzed

| Header Field             | Purpose                                                                                                                                                                             |
| ------------------------ | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `From`               | Identifies the sender of the email and is crucial during the investigation. I can investigate the sender's email address, domain, and associated infrastructure to identify potential indicators of compromise and perform OSINT. |
| `Received`               | Shows email server hops involved in delivering the message. I can use these details to investigate sending infrastructure and perform OSINT on associated domains and IP addresses. |
| `Delivered-To`           | Identifies the recipient address to which the email was delivered.                                                                                                                  |
| `Return-Path`            | Contains the address used for handling email delivery failures (bounces).                                                                                                           |
| `Authentication-Results` | Contains email authentication results, including SPF, DKIM, and DMARC, which help assess whether the message passed authentication checks.                                          |

## What I Learned

* Analyzing raw email content and headers during phishing investigations.
* Decoding Base64-encoded email content and extracting embedded files.
* Identifying file types using hexadecimal signatures (magic numbers).
* Reconstructing files based on their actual file types.
* Extracting metadata from archives and supporting further investigation through email header analysis.

Please refer to the full report for further details on the investigation.
