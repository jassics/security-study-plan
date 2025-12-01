# Common Skills for Cybersecurity Study Plan

Whichever domain you choose in the Cybersecurity umbrella like Application Security, Cloud Security, or DevSecOPs; there are common skills that one must learn to excel in this domain.
I have explained [what you need to learn in those common skills here](https://github.com/jassics/cybersecurity-skills-career-roadmap/blob/master/common-skills.md)

So, I will explain where to study and how much time you should devote to learning those concepts in these common skills so that you are job-ready and interview-ready too!

**These 5 common skills are:**

## ToC
1. [Linux Basics](#linux-basics-and-linux-commands) - 1-2 weeks
2. [Networking Fundamentals](#networking-fundamentals) - 2-4 weeks
3. [Programming Fundamentals](#programming-skills) - 4-8 weeks
4. [Cloud Computing Fundamentals](#cloud-computing) - 3-4 weeks
5. [Essential git commands](#git-commands) - 1 week
6. [Networking matters](#networking-matters)

## Linux Basics and Linux Commands
**Duration: 1-2 weeks**

It should not take more than a week to be comfortable with basic Linux commands to do day-to-day activities.
Once you are comfortable with basic commands, go for networking and other security-related command in little depth.

### Week 1: Basic Commands
Bug bounty hunters, Penetration testers, and almost all tech-focused security professionals use O.S. like Kali Linux, Parrot OS, or BlackArch Linux which have lots of security tools to play with.
But for that, you would need to know the basic workings of Linux and commands.

**Some common (50) commands, I can think of are in alphabetical order:**
1. awk, cat, cd, chmod, chown, cp, curl, dig, du, df
2. echo, export, find, grep, head, history, host, ifconfig, kill, less
3. locate, ls, man, mkdir, more, mount, mv, nslookup, ping, ps
4. pwd, rm and rmdir, scp, sed, service/systemctl, sort, ssh, sudo, tail, tar
5. top, touch, uname, uniq, wget, whois, whatis, w, wc, zip

### Week 2: Security Focused Commands
**Beyond basics commands for security professionals (mainly AppSec and Pentesters) are:**
1. netcat, nslookup, host, dig, netstat, traceroute
2. nmap, nikto, fierce, dirb
3. install/uninstall/update/upgrade
4. find, grep, ifconfig
5. learn the basics of regular expression as well.
6. start and stop services
7. basic understanding of /opt /tmp and log server locations
8. comfortable running scripts written in various languages like Python, ruby, go, etc.

### Resources
**Books**
1. [Linux Basics for Hackers: Recommended](https://www.amazon.in/Linux-Basics-Hackers-Networking-Scripting/dp/1593278551/)
2. [The Linux Command Line](https://www.amazon.in/Linux-Command-Line-2nd-Introduction/dp/1593279523/)
3. [How Linux works](https://www.amazon.in/How-Linux-Works-Brian-Ward/dp/1718500408/)

**Courses**
1. [Introduction to Linux Commands and Scripting](https://www.coursera.org/learn/hands-on-introduction-to-linux-commands-and-shell-scripting)
2. [Linux Fundamentals for Security Practitioners: Recommended](https://www.cybrary.it/course/linux-fundamentals-for-security-practitioners/)

**Videos**
1. [Linux for Ethical Hackers: Recommended](https://www.youtube.com/watch?v=lZAoFs75_cs)
2. [Hacking for beginners: Linux and Common Commands](https://www.youtube.com/watch?v=lZAoFs75_cs)
3. [50 most popular Linux and Terminal Commands](https://www.youtube.com/watch?v=ZtqBQ68cfJc)

## Networking Fundamentals
**Duration: 2-4 weeks**

Except for the Audit and Compliance role, I assume almost every security professional needs to have a basic to intermediate understanding of Computer Networks to excel in its domain.

### Week 3-4: Core Concepts
**I will brief the common concepts here anyway just for quick reference:**
1. IPv4/IPv6, concept of CIDR, IP addressing and subnetting
2. Public vs Private IPs, TCP/IP Model
3. DMZs, Zero Trust Networks
4. Common ports and protocols like 22, 25, ssh, https and so on.
5. Understanding of common cryptographic modules and functions
6. How DNS works, How SSL works

### Week 5-6: Network Security
1. What are the common network threats around these
2. MiTM, Network sniffing
3. Various TCP attacks
4. DoS and DDoS attacks and its preventions
5. Common ideas on firewall or Software-defined networks
6. Basic network troubleshooting like why the internet is slow or down, why wi-fi is not working, open network issues et al.

### Resources
**Books**
1. [See if you know basics as mentioned in this presentation](https://www.ece.uvic.ca/~itraore/elec567-13/notes/dist-03-4.pdf)
2. [Computer Networking: A Top-Down Approach by Kurose and Ross: Recommended](https://www.amazon.in/Computer-Networking-Top-Down-Kurose-James/dp/9332585490/r)
3. [Networking All-in-One For Dummies](https://www.amazon.in/Networking-All-One-Dummies-Doug/dp/1119471605)

**Videos**
1. [Basics of Computer Networking](https://www.youtube.com/watch?v=0j6-QFnnwQk)
2. [Computer Networking Full Course: Recommended](https://www.youtube.com/watch?v=qiQR5rTSshw&t=14s)

**Courses**
1. [Computer Networking by georgia Tech on Udacity: Recommended](https://www.udacity.com/course/computer-networking--ud436)
2. [Bits and Bytes of Computer Networking by Google on Coursera](https://www.coursera.org/learn/computer-networking)

## Programming Skills
**Duration: 4-8 weeks**

Recently, it has become a mandatory skill for any tech security job role to have a decent knowledge of at least one programming language.
Common Programming languages that attract security folks are: Python (recommended), Go (gaining popularity), Ruby.

### Week 7-10: Basics & Projects
**What you should try when you are learning any of these programming languages:**
1. Learn basic concepts
2. Try a few basic projects like 
   1. connecting to DB and get some data
   2. extracting data from a webpage
   3. display some info from the cloud like AWS Instance details region-wise
   4. automate few security stuff like docker monitor, get public IPs, server details, etc
   5. See if you can find any task related to CSV, JSON
   6. Learn the use of crypto modules
   7. simulate a few Linux or other commands to be comfortable with the language like a small nmap simulation

### Week 11-14: Security Focus
1. Understand the OOP concept and at least you should understand others' code comfortably
2. Try to review the source code from a security perspective
3. [Read Python Security Best Practices](https://snyk.io/blog/python-security-best-practices-cheat-sheet/)

### Resources
**Books**
1. [Learn Python 3 the Hard Way](https://www.amazon.in/Learn-Python-Hard-Way-Introduction/dp/0134692888/) - Recommended
2. [Violent Python](https://www.amazon.in/Violent-Python-Cookbook-Penetration-Engineers/dp/1597499579)
3. [Black Hat Python](https://www.amazon.in/Black-Hat-Python-2nd-Programming/dp/1718501129/) - Must Read
4. [Full Stack Python Security](https://www.manning.com/books/full-stack-python-security) - Must for AppSec Professionals
5. [Masterting Python for Networking and Security](https://www.oreilly.com/library/view/mastering-python-for/9781788992510/)

**Videos**
1. [Python Security Best Practices](https://www.youtube.com/watch?v=ZDzDpapddPg)
2. [Security Checks for Python Code](https://www.youtube.com/watch?v=zVIfH89oWno)
3. [Intro to Python for Security Professionals](https://www.youtube.com/watch?v=pFMzgPGfl4w)

**Courses**
1. [Python for Cybersecurity Specialization](https://www.coursera.org/specializations/pythonforcybersecurity)
2. [SEC573: Automating Information Security with Python](https://www.sans.org/cyber-security-courses/automating-information-security-with-python/)
3. [Python for Pentesters](https://www.pentesteracademy.com/course?id=1)

## Cloud Computing
**Duration: 3-4 weeks**

Cloud Computing is everywhere these days be it Industrial, Pharma, Finance, IT etc. 
Sooner or later, it will be a mandatory skills to have for any cybersecurity job roles.

### Week 15-18: Cloud Fundamentals
Learn any of the famous CSPs like AWS, Azure or GCP and 
1. try to understand the use of it to solve various traditional challenges and 
2. then try to understand what are the new security challenges added because of Cloud concepts. 
3. Understand various service and deployment models
4. Shared Security Responsibility
5. Microservices
6. IAM functionalities (Must understand very well)
7. Data Encryption
8. Cloud Networking concept is very important to succeed in Cloud Security

There are separate plans for Cloud Security Study Plan as listed below:
1. [AWS Security Study Plan](aws-security-study-plan.md)
2. [Azure Security Study Plan](azure-security-study-plan.md)
3. [GCP Security Study Plan](gcp-security-study-plan.md)

### Resources
**Books**
1. Cloud Computing for Dummies
2. [AWS in Action](https://www.manning.com/books/amazon-web-services-in-action)

**Videos**
1. [Cloud Computing Playlist by Fkexmind](https://www.youtube.com/playlist?list=PLRTsCutScZnyfH0NLaOJxDEn2ZWZuBlup)
2. [What is Cloud Computing by AWS](https://www.youtube.com/watch?v=mxT233EdY5c)
3. [Inside a Cloud Data Center](https://www.youtube.com/watch?v=XZmGGAbHqa0)

**Courses**
1. [Introduction to Cloud Computing by IBM on Coursera](https://www.coursera.org/learn/introduction-to-cloud)
2. [Micro Masters Program in Cloud Computing](https://www.edx.org/micromasters/usmx-umgc-cloud-computing)

## git commands
**Duration: 1 week**

You must understand any of the Version Control Software and git is one of the famous one at present.
Don't go for gui version like sourcetree rather try to learn and understand common git commands at terminal level.

### Week 19: Git Basics
**Most basic git commands to understand are:**
1. git clone, git add, git commit, git branch, git pull
2. git fetch, git merge, git push, git config, git log

There are many job roles/titles which make it as a mandatory skill, such as: Application Security, Penetration tester, DevSecOps, API Security, Security Engineering.

### Resources
**Books**
1. [Pro Git by Appress](https://git-scm.com/book/en/v2) - Highly recommended
2. [Beginning git and github by Apress](https://techviewleo.com/best-books-to-learn-git-version-control/)
3. [github cheatsheet](https://education.github.com/git-cheat-sheet-education.pdf)

**Videos**
1. [git and github for beginners - crash course by freecodecamp](https://www.youtube.com/watch?v=RGOj5yH7evk)
2. [git fundamentals for beginners - full course for free by Flexmind](https://www.youtube.com/watch?v=zyB-6U7DRKI)

**Courses**
1. [Git Fundamentals for everyone on Udemy](https://www.udemy.com/course/git-basics-for-everyone/)
2. [Version Control with Git by Atlassian on Coursera](https://www.coursera.org/learn/version-control-with-git)
3. [Learn git and github by codecademy](https://www.codecademy.com/learn/learn-git)

## Networking matters
Once you are on track and now understands the heat, it's time to:
1. Make some good LinkedIn contacts from the application security domain.
2. Find a mentor or follow someone who shares blogs, tutorials, talks on these topics.
3. Make connections through various security conference online/offline
4. Publish some good appsec articles, may be basic concepts, but you must publish. Choose medium.com or something of your choice.
5. Join webinars, conferences, newsletters.
6. Help someone who is still a beginner or struggling to understand appsec concepts. You will even learn better while guiding/helping others.

By the time you cover all these checklists, you will be already on a way to have a good start in a web security job role. All the best!

