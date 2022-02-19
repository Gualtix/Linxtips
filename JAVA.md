## Instal JDK in Java jdk-8u202-linux-x64.tar.gz
    
[Source: JavaHelps](https://www.javahelps.com/2015/03/install-oracle-jdk-in-ubuntu.html)
## Set Environment Variable JAVA_HOME

```bash
# Create directory
sudo mkdir /usr/lib/jvm

# Movre to:
cd /usr/lib/jvm

# Untar JDK from its download location
sudo tar -xvzf /home/wrm/jdk-8u202-linux-x64.tar.gz

# Edit Evironment Variable
sudo nano /etc/environment

# Add to the existing PATH variable separated (by a colon) :
/usr/lib/jvm/jdk1.8.0_202/bin
/usr/lib/jvm/jdk1.8.0_202/db/bin
/usr/lib/jvm/jdk1.8.0_202/jre/bin

# Remember to ADD not to REPLACE 
PATH = "SOMETHING:/usr/lib/jvm/jdk1.8.0_202/bin:/usr/lib/jvm/jdk1.8.0_202/db/bin:/usr/lib/jvm/jdk1.8.0_202/jre/bin"

# Add the following environment variables at the end of the file
J2SDKDIR="/usr/lib/jvm/jdk1.8.0_202"
J2REDIR="/usr/lib/jvm/jdk1.8.0_202/jre"
JAVA_HOME="/usr/lib/jvm/jdk1.8.0_202"
DERBY_HOME="/usr/lib/jvm/jdk1.8.0_202/db"

# /etc/environment After Modification:
PATH="/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/games:/usr/local/games:/snap/bin:/usr/lib/jvm/jdk1.8.0_202/bin:/usr/lib/jvm/jdk1.8.0_202/db/bin:/usr/lib/jvm/jdk1.8.0_202/jre/bin"

J2SDKDIR="/usr/lib/jvm/jdk1.8.0_202"
J2REDIR="/usr/lib/jvm/jdk1.8.0_202/jre"
JAVA_HOME="/usr/lib/jvm/jdk1.8.0_202"
DERBY_HOME="/usr/lib/jvm/jdk1.8.0_202/db"

# Enter the following commands to inform the system about the Java's location
sudo update-alternatives --install "/usr/bin/java" "java" "/usr/lib/jvm/jdk1.8.0_202/bin/java" 0
sudo update-alternatives --install "/usr/bin/javac" "javac" "/usr/lib/jvm/jdk1.8.0_202/bin/javac" 0
sudo update-alternatives --set java /usr/lib/jvm/jdk1.8.0_202/bin/java
sudo update-alternatives --set javac /usr/lib/jvm/jdk1.8.0_202/bin/javac

# To verify the setup enter the following commands and make sure that they print the location of java enter:
sudo update-alternatives --list java
sudo update-alternatives --list javac

# Verify the Java version
java -version
```
