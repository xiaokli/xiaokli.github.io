---
layout: post
title: "Share My Linux Setup For Java Development" 
date:   2021-05-08 13:18:21 +0800
categories: java linux 
---

Just want to share the setup of my Linux desktop I used for development( mainly focusing on Java based, including scala for API&spark, kotlin for android).

You can choose any release version of Linux for development, but you would better choose one with active community and popular among Linux users in case you can get supports when you met any issue.

Now Let's get back to our topic, I am a software developer mainly working on Java tech stack based projects, recently I am trying to initiate some side project for myself, I installed a Chrome OS on my old MacBook Air 7,2 and enabled the Linux virtual machine in the Chrome OS for setting up my development workspace.
The Linux version provided by the Chrome OS is Linux with kernal 5.4 it's not important since the software/application installations are similar for Linux release versions. 

If you are a Java developer you may already have known that we what we need to have in our OS, everyone has his/her own habits to manage the required dependencies, I would like to share my practice since it makes me focusing on coding or environment maintaining.

## Install SDKs

Share a little bit tech stack I used in my side project, I build the API service with Play2 framework using scala to implement and SBT to manage the project dependencies and build script. this stack requires me to prepare a well JDK playground here.
Then I turned to useful tool, [SDKMAN](https://sdkman.io/) which can manage parallel JDK and other SDK versions in our Linux BOX.

**Install SDKMAN**, there is very quick and fast way to install SDKMAN to your Linux, just one command, `curl -s "https://get.sdkman.io" | bash` the prerequesites are 1) you should be `cURL` installed, 2) you connected your PC to the internet -_^. now we have have half done on the JDK/SDK installation.

**Install JDK/SDK** you need, you check supported JDK and SDKs by SDKMAN on the website but even most of the SDKs in java tech stack are already included, eg, scala, spark, spring in web API, data processing and Message Queue.

* `sdk ls java` to find the versions supported
* `sdk install java $version` to install the version you want
* `sdk ls` and `sdk install` others you want like scala, sbt ...


## Install IDE

As we all know, Intellij Idea is currently the best java IDE, we will take Jetbrains Intellij Idea as example, but also it applies to how to install eclipse if you want.

If you are using latest ubuntu you can easily install Idea by snap store or you can install snap store then install the idea using snap, but it takes more steps and we need to maintain the snap meanwhile.

IMO, for Application I like to install it instantly, it would be more clear for me where did it install it and I can find it easily clean or upgrading.

* Download a release gz package from official website `curl -sSL https://download.jetbrains.com/idea/ideaIC-2021.2.3.tar.gz -O`, and validate the checksum if you want.
* Extract the package files to `tar -xzf ideaIC-2021.2.3.tar.gz -C /opt`, now you can use it by running `/opt/idea-IC-212.5457.46/bin/idea.sh`
* Now we can add the Application shortcut in the Launcher, most of the Linux release editions list the applications defined in `/usr/share/applications/*.desktop`


```
/usr/share/applications/jetbrains-intellij-idea.desktop

[Desktop Entry]
Version=1.0
Type=Application
Name=IntelliJ IDEA Community Edition
Icon=/opt/idea-IC-212.5457.46/bin/idea.svg
Exec="/opt/idea-IC-212.5457.46/bin/idea.sh" %f
Comment=Capable and Ergonomic IDE for JVM
Categories=Development;IDE;
Terminal=false
StartupWMClass=jetbrains-idea-ce
StartupNotify=true
```

for how to write good desktop entry file please refer to [the wiki page create by ArchLinux](https://wiki.archlinux.org/title/desktop_entries).

Enjoy your time in writing code, have a nice day.
