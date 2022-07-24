# security-learnings-journal
Personal journal for security learnings, I aim to post every day

Sat, Jan 8:

- I did an hour of working on PicoCTF today. I spent a while on the Cookies challenge. Having tried a bunch of other stuff (including seeing if there's some non-GET or POST HTTP method I need to use), I feel fairly confident that it's supposed to be SQL injection. However, none of the typical SQL injection things seem to be working... So I'll probably need to be more creative. So far I've been assuming the query looks something like "SELECT xxx FROM yyy WHERE zzz = query", but perhaps the format is rather different. I moved on to later picoCTF challenges, and did a few very easy ones. No particular learnings unfortunately, except that I got to use Postman for the first time in a while.

Sun, Jan 9:

- I did 20 minutes of PicoCTF today. Ben Lee kindly gave me two hints on the Cookies one. I can't believe I didn't think of editing the cookie!

Mon, Jan 10:

- I did an hour of PicoCTF today. Worked on the Easy Peasy problem about OTP. I can see that the key is used in a rotating manner, and I'm able to consistently "see" a given part of the key, I think... since I can try spamming different kinds of chars and still see a consistent result in the key. However, looks like I'm peeking at the wrong part of the key since I'm not getting anything useful when I xor my key section with the encrypted flag. I also noticed that the key seems to consist mostly of ascii chars saying \xad\x0f etc, which is interesting but may not be useful.

Tue, Jan 11:

- I did around 40 min of learning about log4j today. I read about the vulnerability, which was very easy to understand. I then tried to learn how to replicate the vulnerability. I'm going to first aim to just replicate the basic dns vulnerability, before trying any corrupted LDAP shenanigans. First thing to do is to set up a Java web server on my own machine, so I spent most of the time getting started with that.

Wed, Jan 12:

- I missed today's Focusmate as I had to pick up a friend. I did listen to a bit of the Darknet Diaries today. I was surprised that a Managed Service Provider (MSP) would have such terrible security practices, including failing to revoke credentials from a fired employee.

Thu, Jan 13:

- I did Focusmate today but wasn't very focused. I did make a bit of progress, reading some more of the Apache Tomcat docs, running the provided Tomcat server locally, and installing Ant.

Fri, Jan 14:

- Was focused on Focusmate today, helped that Brittany was next to me. Slow progress on understanding Tomcat. It feels pretty clunky and unintuitive to use so far, and the docs are pretty technical. I only got as far as setting up the basic ant stuff and the basic admin username/password, and starting to set up my basic webapp.

Sat, Jan 15:

- Sorry, missed two updates. I did the Focusmate session working on my Tomcat server. I finally got something "working" as I just copied the sample webapp and modified the files a tad.

Sun, Jan 16:

- Tried getting log4j to run in my Tomcat server but failed. It seems like the Java import system is pretty different from Python, it makes me appreciate pip and I'm guessing maven would help with this too. Spent some time digging around looking for the right things to import. Found some promising jars but still very confused about how I'm supposed to easily know or find the appropriate jars to import, or where to import them.

Mon, Jan 17:

- Some house issues caused me to miss update today, sorry.

Tue, Jan 18:

- I spent a rage-inducing 50 minutes making zero progress on the Tomcat server import errors. At least I figured out that Tomcat should already come with the necessary jars for the HTTPServlet class... But the way ant is set up is totally unintuitive to me, as it doesn't even copy over the basic index.html file when building. WHY????? And, when compiling, ant does seem to verify that it can find the imported classes, yet when that compiled and built software is running in Tomcat it suddenly can't find that class anymore. I'm getting desperate, so I've started downloading and setting up Eclipse. Perhaps it will be easier. I will also post on Facebook asking for help haha.

Wed, Jan 19:

- Spotted an error in my build.xml file, but other than that no progress. I did, however, connect with Joe and pushed my code to Git for him to take a look. He is sending me a working jetty app of his, which I will use as a reference going forward.

Thu, Jan 20:

- Did a terrible job focusing today, but took a look over Joe's jetty project. It looks like he's basically using javac directly, so his project structure is a bit different than mine. However, it suggests I should probably understand the details of javac, and how ant relates to javac, in order to fix my compilation errors.

Fri, Jan 21:

- No update, sorry. Was busy tonight with family stuff.

Sat, Jan 22:

- Started working with jetty today! Only spent a short amount of time, was not focused enough. So far, it's easier than Tomcat and I'll continue with it instead of Tomcat.

Sun, Jan 23:

- Again, no update, sorry.

Mon, Jan 24:

- lol, finally got jetty working! Turns out that my issue was following a log4j v1 tutorial when trying to use log4j v2. I blame unclear error messages, but I should have known to be careful about basics like versioning, and also I should know better than to assume that the error message tells me the source of the problem. I also got log4j working. Will start learning about the LDAP exploitation tomorrow! Thanks so much to Joe for helping

Tue, Jan 25:

- Got to meet, by chance, a really cool security person on Focusmate yesterday! They recommended that I look for people in my area to learn security from/with, including local OWASP chapters. There is one in New York, though it hasn't had a meeting in the past few months, presumably due to omicron, though I'll keep an eye out for meetings there. It also gave me the idea to try and go to a security conference, perhaps with some EA people, for fun.
- Today I worked on learning about LDAP and JNDI and the log4j exploit. LDAP seems pretty intuitive, as a way to access and modify directory structures, though I still don't know any details about actually running such a server. I also looked through some of itzbenz's example Log4Shell exploit. It somewhat made sense to me.
- Tried inserting a JNDI query on my local Jetty server and it didn't do anything, I think. Next steps are probably to figure out how to set up my own LDAP server (or copy itzbenz's), and then figure out what's missing in my local Jetty server that's causing the JNDI to fail

Sun, Jan 30:

- I took a break for a few days, I think it was good for me to recharge. :)
- Today I migrated over from my super-jank jetty setup to just using my Tomcat and ant setup. The "error" I was seeing before was just log4j version issues, so migrating didn't end up being very difficult. I am also getting a bit more comfortable with the build.xml in ant.
- I also started looking at itzbenz's sample attack LDAP server. Next session I hope to get log4j logging to an external file so I can inspect the results, then I will try setting up a sample LDAP server.

Tue, Feb 1:

- I fixed my import error in Tomcat today, so my Tomcat servlet works. I'm honestly not sure where I was supposed to figure out that javax had been renamed to jakarta haha. Now working on getting log4j to log to an external file.

Wed, Feb 2:

- log4j is working now, logging to an external file so I can see the logs!

Tue, Mar 22:

- Woah it's been a while, sorry about that. Today I dusted the cobwebs off the log4j project, happy to see logging works fine. I looked into learning about Active Directory before doing this LDAP server, but after a bit of Googling, that seems like overkill. I decided to proceed with learning LDAP through the ldap.com tutorial, which seems fairly readable, and I spent a bit of time getting started on that.

Wed, Mar 23:

- Learned some basic LDAP concepts, such as DN's, RDN's, searches, and attributes.

Sat, Mar 26:

- Read more about LDAP schemas. First read about OID's, in which I learned that OID's are meant to be hierarchical but globally unique. Therefore, any organization should request its own OID base. Next learned about attribute syntaxes, which are the LDAP equivalent of data types. It seems like all the expected types are available, but specified with somewhat-obscure OID's. Similarly goes for matching rules. Doesn't seem like I will ever need to worry about creating these, just using them. Attribute types seem slightly more useful to know how to create, but after reading the LDAP docs I'm still pretty confused about what a typical LDAP server setup looks like, though I do have a much better grasp of some of the basic concepts like OID's, and schema items each being a description of a data type, comparison rule, or class.
- Also, realized that the UnboundID LDAP SDK for Java is meant to faciliate LDAP clients, not run an LDAP server lol. So now I need to look into how to run an LDAP server.
- Next thing to read is how to use the in-memory directory server from UnboundID https://docs.ldap.com/ldap-sdk/docs/in-memory-directory-server.html

Wed, Apr 6:

- Learned more about the in-memory directory server from UnboundID LDAP. Also learned that the LDAP server used by benz is not that legit, since it's manually intercepting the LDAP request. Therefore, I'm planning to take a different approach and set up the actual LDAP server, not using benz approach. That way I'm hoping to get a bit more understanding of how LDAP servers can work.

Thu, Apr 7:

- Learned that JNDI is not the same thing as LDAP LOL. Also realized that setting up the LDAP server to handle the JNDI query properly is non trivial. Saw another implementation of log4Shell and like itzbenz's, it does not use a legit LDAP mechanism to respond to the JNDI but instead hijacks the request early on. https://github.com/leonjza/log4jpwn/blob/master/pwn.py Therefore, I'm suspecting I either need to understand LDAP better, or just take the hijack approach.

Fri, Apr 8:

- Learned about how JNDI can be used with LDAP, and better understood how to write my own LDAP server to cooperate with a JNDI query. Still a bit confused about why itzbenz and others are using intercepts intead of the native LDAP API because it seems like JNDI should play pretty nicely with LDAP. However, I'm still unclear on how to Java class served from LDAP server should be encoded.

Sun, Jun 19:

- Fell off the horse again, in regards to updating this regularly. In the past few months I've been reading "The Art of Software Security Assessment", a book by Dowd, McDonald and Schuh. I read the sections on how to structure a software security audit and general strategies to build understanding of a codebase and identify weak points. However, I will probably need a second read-through of these sections in order to better internalize them.
- Today I spent time reading the chapter about the IP protocol. The book went over some examples of flawed C code which poorly handled IP packets, particularly with how the IP header information was processed. It seems like accidental buffer overflows or unsigned integer underflows are very easy to accidentally do in C!

Mon, Jun 20:

- Today I listened to some of an 80K podcast with Nova DasSarma about information security and AI. One interesting thing I learned is how military software is sometimes developed in SCIF's, which block wireless communication and require even basic stuff like code documentation to all be carried inside.

Sun, Jun 26:

- Today I reviewed RSA and Diffie-Hellman. I forced myself to write them from memory, which I hope will help me remember. I also started reading Kaspersky's recent report on common TTP's of modern ransomware groups. It seems like the most common entrypoints are insecurely configured RDP gateways, phishing with malicious attachments or links, and external-facing services like VPN's, Citrix gateways, etc. Also, it's interesting that Kaspersky lists some recommended things to monitor as anomalous activity. I'm guessing that Bloomberg already monitors such things, and that the Threat Detection team would be on top of such reports.

Mon, Jul 4:

- Continuing to read Kaspersky's report on ransomware groups. One interesting thing is that malicious Microsoft Office macros are still a very common method, even though they are well known at this point and Microsoft Office explicitly asks you whether to enable macros. It seems, at least, that the step from user opening attachment to attacker gaining a system shell continues to be non-trivial, since the macro attack seems rather non-optimal to me from a usability perspective, as the user must first decide to open the attachment and also decide to enable macros in the document. I'd be curious to see what percent of users open the email but decide not to open attachment, or decide not to enable macros.
- Kaspersky notes that alarms should be raised if a trusted file handler such as Microsoft Office, PDF, etc. is seen running a shell, downloading a file, executing a library, or opening a network connection. Note that the "malicious file" method is almost always through phishing. If you find a vulnerable RDP opening or other public opening, then you can go directly to exploitation without a macro.
- Interestingly Kaspersky dedicates a section to general "Command and Scripting Interpreter", which seems a bit obvious since it makes sense that you'd eventually want a shell. I did learn about Empire Powershell, though I'm still a bit unclear about what its purpose is.
- WMI (Windows Management Instrumentation) is an orchestration tool for Windows, often used by sysadmins (reminds me of something like Terraform). Often also used by attackers to execute commands, such as deleting backups during ransomware attacks. It's very powerful: for example, it can be used to search through all running processes and delete any matching a given name or containing a certain word. It's often used for lateral movement, with commands of the form wmic /node:...
- Also, apparently Shadow Copy is a Windows tool often used for backups?
- Moving on to the next section of the report. The previous sections were about initial entry and tools for executing commands in the target environment. Next up is persistence: how the attacker is able to establish a foothold in the environment long-term?
- Seems like, often, the attacker sets up a scheduled task (windows equivalent of a cron job). Note, this often means the malware file itself is publicly visible as a scheduled task, so you can scrutinize scheduled tasks to look for anomalies. The same goes for tasks which run on startup or logon (in the case of Windows, tasks which run on logon are called Run Keys, and live in the Registry). The attackers may do some basic protections like hiding the file as well, so don't forget to check for that.
- Attackers also use BITS for a similar purpose, and jobs run by bitsadmin are pretty hard to detect as they are stored in a database, not on disk. However, you can potentially look at the command line arguments often used by attackers for bitsadmin, such as /create and /download and /transfer.
- Typically, an attacker will want/need to create an admin account. Keep an eye out for new account creation, particularly if it's done on the command line (the real sysadmins will typically use a GUI).
- Two tools that seem really popular in ransomware are CobaltStrike and Empire PowerShell, they seem to be mentioned very frequently.
- Attackers often masquerade as a Windows service. In that situation, they often choose an innocuous process name like "WindowsProtectionService" or "Java Updater". Be suspicious of any Windows Services which are in an open writeable directory, or that are unsigned, or are created by a user in an unusual manner.
- Finished the Persistence section, though I should definitely learn more about CobaltStrike and Empire PowerShell.
- Okay I read a little about CobaltStrike Beacon. Seeing as it provides important capabilities like keystroke recording, running shell scripts, taking screenshots, downloading files, and more, I can see why the ransomware groups are using it so extensively lol. It seems incredibly convenient as a tool.
- Next up in Kaspersky's ransomware TTK's outline is Privilege Escalation. While Kaspersky outlines a few example methods, the detection rules they suggest seem like they would probably be quickly outdated as the particular privilege escalation tactics may vary over time? The key seems to be that some form of privilege escalation attack will occur, through exploiting known Windows bugs.
- I looked through the 2014 privilege escalation tutorial for Windows from FuzzySecurity: https://www.fuzzysecurity.com/tutorials/16.html It was very nicely organized and it was interesting that the strategy seems something like "try a lot of quick things to see if the local admins messed up" and also "check the patch history and then check if any known exploits are still unpatched". This makes sense to me.

Thu, Jul 14

- Reading further into Kaspersky's Privilege Escalation section, it sounds like Microsoft server products just regularly have zero day vulnerabilities that allow privilege escalation (e.g. Exchange Server). So it doesn't seem very feasible to prevent privilege escalation in these products: better to focus on other areas of defense perhaps?
- It can be worth monitoring when an unusual permission or access is granted to a process, though.

Fri, Jul 15

- Every ransomware group uses existing Windows commands to download and run their code, in order to avoid restrictions and antivirus. Presumably, antivirus and monitoring are more lenient when the program being executed is a Windows program itself. Examples include mshta.exe which can download and execute Internet Explorer scripts, and msiexec.exe which can download and execute installer scripts.
- Futhermore, exploiting these scripts is pretty easy once you've figured out a way, because it can be automated into a script.
- As a defender, watch out for unusual behavior from Windows-signed programs: downloading and executing code, or executing code from a public-writable directory, spawning shell, opening unusual filetype, etc.

Sun, Jul 17

- Another common pattern is process hollowing: start a (typically Windows system) process and then inject malware into the memory location of the process. This can avoid a lot of detection methods because often SIEM solutions are configured to ignore Windows system processes. Common processes to inject into are regedit.exe and werfault.exe.
- The CreateRemoteThread event in Sysmon logs can indicate injection is occurring?
- SIEM logs aren't as useful for detecting process injection.
- Typically, the easiest way for ransomware to bypass system firewall is to modify it directly with a command like netsh or NetFirewallRule. So it can definitely be worth adding a detection rule monitoring when these commands are executed. (Note that there are more subtle ways to get around firewalls though, so don't assume this is foolproof detection.)
- Typically, a ransomware will aim to disable security features like Raccine and Windows Defender. Therefore, any time these are disabled or modified by system, it is a red alert for suspicious activity.
- Ransomware also typically tries to masquerade as legitimate processes. Watch out for cases where a system utility is launched from an atypical directory, or a file is created with the same name as a system file, or unusual system utilities launch flags.

Mon, Jul 18

- Attackers also typically delete their own files after execution, and also try to clear system logs. There are some methods to try and restore system logs after deletion, but I did not look into them.

Thu, Jul 21

- If you're relying on pattern matching in scripts to detect malicious behavior, keep in mind that attackers will often use some form of encoding (e.g. base 64) to obfuscate their scripts.
- However, you may be able to detect obfuscation itself as malicious.
- That concludes the section on Defense Evasion. To summarize, attackers typically try to hide, delete, or obfuscate their programs. When they need something to run regularly, they will typically use process hollowing or other ways to look similar to a system process. Keep an eye out for processes which look like system processes, but with some unusual factor such as running location or what kind of requests it is making.
- The next section is on Credential Access. It seems like LSASS memory (a Windows memory store which includes encrypted passwords and hashes of passwords (NT and LM hashes)). Note that multiple Windows processes can dump LSASS memory as long as they are running in privileged account, including Task Manager. Note that it seems like tools like Mimikatz continue to work for this purpose as well.
- However, these techniques do seem to leave a Sysmon log behind, which can be used for detection (Process Accessed log).
- I don't fully understand the mitigations Kaspersky recommends in this section so I'll need to look more into it.

Fri, Jul 22

- Another common method for getting credentials, besides LSASS memory, is exfiltrating them from the browser. Apparently this is fairly easy (just need to look in the Program Files in the correct spot).
- Brute force is also extremely common. So absolutely set rate limits on all password tries, e.g. per IP.
- That concludes the section on Credential Access. Seems like browsers, LSASS, or brute force are all common and fairly intuitive (except for LSASS, which I still don't fully understand).
- The next section is Discovery: how do attackers find attack targets further in the network and how do they decide where to move next? Notably, every technique in this section was used by every ransomware group, so there is a lot of shared techniques here.
- One great, simple discovery tool is checking existing connections on the host machines. Example commands include "netstat -ano", "net session", "net use", "query session".
- A related method is using system info to find other systems. For example, "arp -a" is used by EVERYONE. It shows you the system ARP cache which maps IP's to MAC's. Another common command is "net view /all". Some tools like Lockbit and BloodHound and Powersploit also help with finding remote system.
- Same goes for shared network drives. In general, any info about the network structure is useful. The relevant commands are "net share" and "net view".
- Similarly, attackers will want to look at what accounts are available so they know what privileged accounts they can target. Example commands include "whoami /groups", "net group ..." etc.
- If you see a process searching for files like "*.pdf", that's a major red flag for ransomware. They will often try and do file discovery with the Windows API, so an EDR(?) solution may be necessary. Not sure I understand this part, though.
- Finally, one last thing I wasn't aware of at all, is that ransomware will try and terminate all other processes when encrypting files. The reason is, it would be bad if a file was locked by another program and therefore wasn't encrypted. So keep an eye out for process enumeration like "tasklist.exe"

Sat, Jul 23

- RDP is often used for lateral movement. It should be disabled wherever possible, and where enabled, the list of accounts which are authorized for RDP should be monitored and limited.
- For external RDP servers, always require multi-factor authentication, use firewall rules, and rate limiting. Also alert on suspicious connection times or locations.
- Kaspersky notes that some common tools for lateral file transfers include psexec, SMB, bitsadmin, and AnyDesk. However, while you can monitor these and disable them when not needed, in general it probably makes more sense to try and guard the admin credentials and privileges instead, because once an attacker has those, a variety of tools can be used for lateral file transfer.




