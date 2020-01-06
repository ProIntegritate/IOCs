# IOCs
Indicators of compromise, scraped from URLHaus links and other sources

For maximum compatibility (Forensics, SIEM, Threathunting platforms) the following formats are supported:

- MD5
- SHA1
- SHA256
- FUZZYHash
- File ID (Type)
- Filesize
- Richheader Similarity hash* (Added from 2020-01-01, if not found (i.e. an ELF, Script, MSI, RTF, DOC or whatever) a "-" will be shown) 

* Please note that the RichHash isn't likely to be compatible with other implementations of a PE RichHas, mostly because i have nothing to test against. Feel free to contact me on twitter if you have a 1) sort-of-standard tool that can generate a RichHash and 2) some tool that use RichHash to detect something. If you provide that, i can create a compatible version of RichHash. Right now i cannot find anything.
