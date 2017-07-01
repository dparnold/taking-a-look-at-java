# taking-a-look-at-java
## What I need ##
1. Setting up java on Linux:
  `sudo apt-get install openjdk-8-jdk`
2. Installing eclipse IDE:
  `sudo apt-get install eclipse`
3. Create the HelloWorld program:

  Open eclipse -> Help -> Cheat Sheets -> Java Developement -> Create a Hello World application

## Compiling and Excecuting without eclipse ##
1. Compiling:
  `javac HelloWorld.java`
2. Excetuting:
  `java HelloWorld`
 
## Things I have learned ## 
### Problem with a symbolic link to java ###
 
 The command: 
  `file /etc/alternatives/java /etc/alternatives/javac`
 gave me the following output:
 
  `/etc/alternatives/java:  broken symbolic link to /usr/lib/jvm/java-9-openjdk-amd64/bin/java`

  `/etc/alternatives/javac: symbolic link to /usr/lib/jvm/java-8-openjdk-amd64/bin/javac`

Therfore the command java would not work


To fix this, I removed the symbolic link and created the correct one to openjdk 8:

 ` rm {link-name}`
  
  `ln -s {/path/to/file-name} {link-name}`
  
  `sudo rm /etc/alternatives/java`
  
 `sudo ln -s /usr/lib/jvm/java-8-openjdk-amd64/bin/java /etc/alternatives/java`

### Problem using ArrayList<Integer> ###
I needed to change the compiler compliance level from 1.2 to at least 1.5 in **eclipse**.

This is done by:

richt click on project -> Properties -> Java Compiler

Then `ArrayList<Integer> arraylist = new ArrayList<Integer>();` is working
