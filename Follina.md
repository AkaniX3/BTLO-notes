# Follina | 10pts | Challenges

Q 1) What is the SHA1 hash value of the sample?
=> Using the cmd to get the sha1 hash value of the file
```
$ sha1sum sample.doc
```
which is, 06727ffda60359236a8029e0b3e8a0fd11c23313

Q 2) According to VirusTotal, what is the full filetype of the provided sample? (Format: X X X X) 
=> Uploading file on the [Virustotal](https://www.virustotal.com/gui/home/upload) it fetches with a lot of info about the file.
(image upload)
which is, Office Open XML Document 

Q 3) Extract the URL that is used within the sample and submit it
=> Well Virutotal also gave this information
So there's that, www.xmlformats.com
But, for checking this we use [any.run](https://any.run/) for checking where this file would 

Q 4) What is the name of the XML file that is storing the extracted URL?
=> Using the binwalk cmd
```
$ binwalk sample.doc
```
(image upload)
it tells us that the file has hidden files inside it,
so unzipping it we find more files, on checking these, we find, document.xml.rels has all the URLs stored in it.

Q 5) The extracted URL accesses a HTML file that triggers the vulnerability to execute a malicious payload. According to the HTML processing functions, any files with fewer than <Number> bytes would not invoke the payload. Submit the <Number>
=> I had no idea about this so I had to search it up, I came to know the files won't fire if it's fewer than 4096 bytes.

Q 6) After execution, the sample will try to kill a process if it is already running. What is the name of this process?
=> msdt.exe

Q 7) You were asked to write a process-based detection rule using Windows Event ID 4688. What would be the ProcessName and ParentProcessname used in this detection rule? [Hint: OSINT time!] (Format: ProcessName, ParentProcessName)
=> msdt.exe, winword.exe

Q 8) Submit the MITRE technique ID used by the sample for Execution [Hint: Online sandbox platforms can help!]
=> VirusTotal gave the answer for this as well, which is T1059

Q 9) VirusTotal gave the answer for this as well, which is CVE-2022–30190
