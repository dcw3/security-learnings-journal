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

Fri, Jan 19:

- Spotted an error in my build.xml file, but other than that no progress. I did, however, connect with Joe and pushed my code to Git for him to take a look. He is sending me a working jetty app of his, which I will use as a reference going forward.
