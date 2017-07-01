# taking-a-look-at-java
1. Setting up java on Linux:
  sudo apt-get install openjdk-8-jdk
2. Compiling:
  javac HelloWorld.java
3. Excetuting:
  java HelloWorld
 
 I had a problem with a symbolic link to java:
 
 The command: file /etc/alternatives/java /etc/alternatives/javac
 gave me the following output:
 
/etc/alternatives/java:  broken symbolic link to /usr/lib/jvm/java-9-openjdk-amd64/bin/java

/etc/alternatives/javac: symbolic link to /usr/lib/jvm/java-8-openjdk-amd64/bin/javac

Therfore the command java would not work


To fix this, I removed the symbolic link and created the correct one to openjdk 8:

  rm {link-name}
  
  ln -s {/path/to/file-name} {link-name}
  
  sudo rm /etc/alternatives/java
  
  sudo ln -s /usr/lib/jvm/java-8-openjdk-amd64/bin/java /etc/alternatives/java

  

