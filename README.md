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
