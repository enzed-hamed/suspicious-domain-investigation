# Suspicious Domain Investigation
By one of my professors I was tasked to investigate a suspicious domain. I spent a few weeks working on the subject. I used techniuqes in multiple areas of cybersecurity including OSINT, Malware Analysis, Web Security, etc, in order to fully investigate the attach chain which led to identifying the origin of the malware, and reported my findings on a weekly basis in form of three documents.
This is a step by step explanation of what I did.
1. I found javascript code served on this domain and performed static analysis
2. Performed dynamic analysis using services like any.run
  So far I found that this script serves popups to users with innocent urls of arbitrary websites.
3. Then fingerprinted Script by identifying some unique strings.
4. Did a simple google search for the fingerprint and other domains serving this code.
5. Follow up investigation led me to finding out the malware was placed into websites by a wordpress extension (for showing amazon products).
6. Researching on the app, I found the app in wordpress store and the PHP source code for it was opensource
7. I statically analysed the code and found:
. Developers of the original wordpress extension were NOT malicious actors
. The code referenced and loaded a dynamic library on another domain
. In 2017, this domain was bought by real attackers and repurposed to serve malicious code
6. Doing OSINT on bad actors, I found that they were selling SEO services, and in fact exploiting wordpress extension was a done to create a SEO botnet campaign which serves normal users visiting victim websites using spoofed wordpress extension with the website links of people buying SEO service
