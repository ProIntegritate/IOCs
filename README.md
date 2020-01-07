# IOCs
Indicators of compromise, scraped from URLHaus links and other sources

For maximum compatibility (Forensics, SIEM, Threathunting platforms) the following formats are supported:

- MD5
- SHA1
- SHA256
- FUZZYHash
- File ID (Type)
- Filesize
- Richhash (Richheader), if not found (i.e. an ELF, Script, MSI, RTF, DOC or whatever) nothing will be shown here.
  If a richhash wasn't found in the executable PE, the section betwee 0x80 to 0xff will be hasbed and "missing"
  will be shown in state (below). It can still be used to pivot on - it's just not very precise.
- Richhash Filename
- Richhash State: "Full header" + (size) or "No header" 

*Note: From 2020-Jan-08 Richhashes are compatible with YARA rules, before that they used ANOTHER format which _wasn't compatible_ and could only be used for pivoting within the data. Will release proper hashes of the files with proper richheader hashes later on.*
