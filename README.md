# IOCs
Indicators of compromise, scraped from URLHaus links and other sources

Latest (daily) IOCs can be found here: https://pastebin.com/u/Purplestuff


For maximum compatibility (Forensics, SIEM, Threathunting platforms) the following formats are supported:

- MD5
- SHA1
- SHA256
- FUZZYHash
- File ID (Type)
- Filesize

V2 addition:
- Yara compatible Richhash (1), V2. Added on 2020-01-07. (Earlier is incompatible with Yara)

V3 addition:
- Metahash (Hash of FileversionInfo strings)


(1) The RichHash field  will be show as:

- rh: MD5_HASH = File contained a RichHash, it was successfully decoded using the XOR key.
- nh: MD5_HASH = File did not contain a RichHash, but the area 0x80 to 0xff was hashed with and presented instead.
- \- = This was not an Windows executable PE file and no data was produced.
  
(2) The Metahash is a product of the following FileVersionInfo strings (as is, no separators):
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


*The new files are called **iocs_V3_yyyy-mm-dd**, **V3** denoting that the new fields and format are in use*

*Note: From 2020-Jan-07 Richhashes are compatible with YARA rules (pe.rich_signature.clear_data), before that they used ANOTHER format which **wasn't compatible** and could only be used for pivoting within the data.*


