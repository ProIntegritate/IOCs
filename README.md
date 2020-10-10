# IOCs
Indicators of compromise, scraped from URLHaus links and other sources

Recent (daily) IOCs can be found in the Recent folder.


For maximum compatibility (Forensics, SIEM, Threathunting platforms) the following formats are supported:

- MD5
- SHA1
- SHA256
- FUZZYHash
- File ID (Type)
- Filesize


V2 addition: (Added on 2020-01-07)
- Yara compatible Richhash (1)

The RichHash field  will be show as:

- rh: MD5_HASH = File contained a RichHash, it was successfully decoded using the XOR key.
- nh: MD5_HASH = File did not contain a RichHash, but the area 0x80 to 0xff was hashed with and presented instead.
- \- = This was not an Windows executable PE file and no data was produced.

*NOTE: From 2020-Jan-07 Richhashes are compatible with YARA rules (pe.rich_signature.clear_data), before that they used ANOTHER format which **wasn't compatible** and could only be used for pivoting within the data.*


V3 addition: (Added on 2020-02-01)
- Metahash (2) Hash of FileversionInfo strings

The Metahash is a product of concatenating the following FileVersionInfo strings (as is, no separators):
- CompanyName
- FileDescription
- InternalName
- LegalCopyright
- LegalTrademarks
- OriginalFilename
- ProductName

Shown as:
- mh: MD5_HASH = File contains FileVersionInfo (at least one string)
- \- = Contains absolutely no FileVersionInfo strings.

Like Richhash, Metahash can and has been quite useful to pivot on unknown malware samples and corellate between samples over time.


*NOTE 1: A very low amount (single digit) of these files are legitimate non mallicious files, like PuTTY which is by itself harmless and a legitemate tool, but sometimes tools are abused and become part of a malware campaign, if you find a legit tool and nobody know why it is there, you should investigate.*

*NOTE 2: The new files are called **iocs_V3_yyyy-mm-dd**, **V3** denoting that the new fields and format are in use*
