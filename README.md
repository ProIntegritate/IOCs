# IOCs
Indicators of compromise, scraped from URLHaus links and other sources

For maximum compatibility (Forensics, SIEM, Threathunting platforms) the following formats are supported:

- MD5
- SHA1
- SHA256
- FUZZYHash
- File ID (Type)
- Filesize
- Yara compatible Richhash (1), added on 2020-01-07. (Earlier data from 2020-jan-01 and onwards is incompatible with Yara)

(1) The RichHash field  will be show as:

- rh: MD5_HASH = File contained a RichHash, it was successfully decoded using the XOR key.
- nh: MD5_HASH = File did not contain a RichHash, but the area 0x80 to 0xff was hashed with and presented instead.
- \- = This was not an Windows executable PE file and no data was produced.
  
*Note: From 2020-Jan-07 Richhashes are compatible with YARA rules (pe.rich_signature.clear_data), before that they used ANOTHER format which **wasn't compatible** and could only be used for pivoting within the data.*

*The new files are called **iocs_V2_yyyy-mm-dd**, **V2** denoting that the new fields and format are in use*

Latest stuff can be found here: https://pastebin.com/u/Purplestuff
