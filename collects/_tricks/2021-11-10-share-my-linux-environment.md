---
layout: post
title: "Linux Setup For Java Development" 
date: 2021-05-08 13:18:21 +0800
categories: java linux 
---

> I would like to share a setup of linux for java development in this post. I think every engineer has his/her tricks when setup their work tools, this is my trick.

You can choose any distribution of Linux as your development operating system, but I would suggest to choose one with active community and popular among Linux users so that you can get supports in case you met any issue.

If you are a Java developer you may already have known that we what we need to have in our OS, everyone has his/her own habits to manage the required dependencies, I would like to share my practice since it makes me focusing on coding rather than environment maintaining.

## Install SDKs

I use [SDKMAN](https://sdkman.io/) to manage my JDK, with SDKMAN I can install and swith between multiple versions of JDK and other SDK easily.

**Install SDKMAN**, there is very quick and fast way to install SDKMAN to your Linux, just one command, `curl -s "https://get.sdkman.io" | bash` . The only prerequesites are:

1. have your linux with `cURL` installed,
2. have your device connected to the internet -_^.

**Install JDK/SDKs** as you need, you can check supported JDK and SDKs by SDKMAN from the official website, and most of the SDKs with java tech stack are already included, eg, scala, spark, spring in web API, data processing and Message Queue.

* `sdk ls java` to find the versions supported
* `sdk install java $version` to install the version you want
* `sdk ls` and `sdk install` others you want like scala, sbt ...


## Install IDE

As we know, the Intellij Idea is one of the most popular java IDE, we will take Jetbrains Intellij Idea as an example to show you how to install desktop application to linux manually.

If you are using latest ubuntu you can easily install Idea by snap store or you can install snap store then install the idea using snap, but it takes more steps and we need to maintain the snap meanwhile.

When I want to install an application, I would like to know more in details about the installation path, configuration path for further maintain, debug purpose.

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