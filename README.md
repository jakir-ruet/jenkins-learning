[![LinkedIn][linkedin-shield-lapissoft]][linkedin-url-lapissoft]
[![Facebook-Page][facebook-shield-lapissoft]][facebook-url-lapissoft]
[![Youtube][youtube-shield-lapissoft]][youtube-url-lapissoft]

## Visit Us [Lapis Soft](http://www.lapissoft.com)

### Get started with Jenkins

***Prerequisites***
To follow this tutorial, you will need:
1. Ubuntu Server 22.04 server configured with a non-root user and firewall.
2. OpenJDK 11 or upper

#### Java & OpenJDK Install
##### [Open JDK Install](https://jdk.java.net/21/)

```bash
apt update
java -version
cd /opt
# as per your OS you should download specified version. my case aarch64.
wget https://download.java.net/java/GA/jdk21.0.2/f2283984656d49d69e91c558476027ac/13/GPL/openjdk-21.0.2_linux-aarch64_bin.tar.gz
tar zxvf openjdk-21.0.2_linux-aarch64_bin.tar.gz
mv jdk-21.0.2 java-21
whereis java # searching if required
find /opt/java-21/java-1.21* | head -n 3 # searching if required
nano .profile 
JAVA_HOME=/opt/java-21 # set java path variable
PATH=$PATH:$HOME/bin:$JAVA_HOME/bin
export PATH
source .profile
java --version
echo $PATH
echo $JAVA_HOME
```

#### [Install](https://www.jenkins.io/doc/book/installing/linux/) Jenkins LTS.
```bash
wget -O /usr/share/keyrings/jenkins-keyring.asc \
  https://pkg.jenkins.io/debian-stable/jenkins.io-2023.key
echo deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc] \
  https://pkg.jenkins.io/debian-stable binary/ | tee \
  /etc/apt/sources.list.d/jenkins.list > /dev/null
```
```bash
apt-get update
apt-get install jenkins
service jenkins status
```

Firewall Configuration
```bash
ufw allow 8080
ufw allow OpenSSH
ufw enable
ufw status
```

Use the following command to get the password
```bash
cat /var/lib/jenkins/secrets/initialAdminPassword
```
After getting the initial password and put required information & selecting plugins we will configure jenkins.
```bash
http://localhost:8080
```
if its need
```bash
apt apt upgrade jenkins-lts
```

Setup JDK
```bash
https://openjdk.org/install/
https://jdk.java.net/21/
wget https://download.java.net/java/GA/jdk21.0.2/f2283984656d49d69e91c558476027ac/13/GPL/openjdk-21.0.2_linux-x64_bin.tar.gz
tar zxvf openjdk-21.0.2_linux-x64_bin.tar.gz

find /usr/lib/jvm/java* | head -n 3
/usr/lib/jvm/java-1.21.0-openjdk-amd64
/usr/lib/jvm/java-21-openjdk-amd64
/usr/lib/jvm/java-21-openjdk-amd64/release

JAVA_HOME=/usr/lib/jvm/
PATH=$PATH:$HOME/bin:$JAVA_HOME
export PATH
source .profile
echo $JAVA_HOME
java --version
Add JDK
JAVA_HOME
/usr/lib/jvm/
```

Github
- install github plugin from plugin management
- configure from tool management

[Maven install](https://maven.apache.org/install.html)

cd /opt
```bash
wget https://dlcdn.apache.org/maven/maven-3/3.9.6/binaries/apache-maven-3.9.6-bin.tar.gz
tar zxvf apache-maven-3.9.6-bin.tar.gz 
mv apache-maven-3.9.6 maven
```

cd maven
```bash
nano .profile
M2_HOME=/opt/maven
M2=/opt/maven/bin
PATH=$PATH:$HOME/bin:$JAVA_HOME:$M2:$M2_HOME
export PATH
source .profile
echo $M2_HOME
mvn --version
```

- create maven app
- push to github & integrate to jenkins

### Working Principle

![Working Principle](./img/working-principle.png)

## Courtesy of Jakir

[![LinkedIn][linkedin-shield-jakir]][linkedin-url-jakir]
[![Facebook-Page][facebook-shield-jakir]][facebook-url-jakir]
[![Youtube][youtube-shield-jakir]][youtube-url-jakir]

### Have a good day, stay with me
<!-- Personal profile -->

[linkedin-shield-jakir]: https://img.shields.io/badge/linkedin-%230077B5.svg?style=for-the-badge&logo=linkedin&logoColor=white
[linkedin-url-jakir]: https://www.linkedin.com/in/jakir-ruet/
[facebook-shield-jakir]: https://img.shields.io/badge/Facebook-%231877F2.svg?style=for-the-badge&logo=Facebook&logoColor=white
[facebook-url-jakir]: https://www.facebook.com/jakir-ruet/
[youtube-shield-jakir]: https://img.shields.io/badge/YouTube-%23FF0000.svg?style=for-the-badge&logo=YouTube&logoColor=white
[youtube-url-jakir]: https://www.youtube.com/@mjakaria-ruet/featured

<!-- Company profile -->

[linkedin-shield-lapissoft]: https://img.shields.io/badge/linkedin-%230077B5.svg?style=for-the-badge&logo=linkedin&logoColor=white
[linkedin-url-lapissoft]: https://www.linkedin.com/company/lapis-soft/
[facebook-shield-lapissoft]: https://img.shields.io/badge/Facebook-%231877F2.svg?style=for-the-badge&logo=Facebook&logoColor=white
[facebook-url-lapissoft]: https://www.facebook.com/GoLapisSoft/
[youtube-shield-lapissoft]: https://img.shields.io/badge/YouTube-%23FF0000.svg?style=for-the-badge&logo=YouTube&logoColor=white
[youtube-url-lapissoft]: https://www.youtube.com/@LapisSoft/featured


