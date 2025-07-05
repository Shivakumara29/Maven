Install Maven on Ubuntu with APT   Main LINk (https://phoenixnap.com/kb/install-maven-on-ubuntu))

sudo apt update
sudo apt install maven -y
mvn -version

Step 1: Install OpenJDK
sudo apt update
sudo apt install default-jdk -y
java -version

Step 2: Download and Install Maven
1. Visit the Maven download page.https://maven.apache.org/download.cgi 
3. Right-click the version of Maven you want to install and copy the link.
4. wget https://dlcdn.apache.org/maven/maven-3/3.9.10/binaries/apache-maven-3.9.10-bin.tar.gz

Copying the link to the latest Maven version.
 Once the download is complete, extract the installation file to the /opt directory:

sudo tar xf /tmp/apache-maven-*.tar.gz -C /opt
Copy
5. Create a symbolic link leading to the Maven installation directory:

sudo ln -s /opt/apache-maven-[version] /opt/maven
Copy
Replace [version] with the Maven version you downloaded. For example:

sudo ln -s /opt/apache-maven-3.9.6 /opt/maven
Copy
Step 3: Set Up Environment Variables
1. Use a text editor like Nano to create and open the maven.sh script file in the /etc/profile.d/ directory:

sudo nano /etc/profile.d/maven.sh
Copy
2. Add the following lines to the maven.sh file:

export JAVA_HOME=/usr/lib/jvm/default-java
export M2_HOME=/opt/maven
export MAVEN_HOME=/opt/maven
export PATH=${M2_HOME}/bin:${PATH}
Copy
Creating the maven.sh script file.
Save the file and exit.

3. Use the chmod command to make the maven.sh file executable:

sudo chmod +x /etc/profile.d/maven.sh
Copy
4. Execute the maven.sh script file with the source command to set up the new environment variables:

source /etc/profile.d/maven.sh
Copy
Step 4: Verify Maven Installation
Check the current version of Maven to verify the installation:
mvn -version
Copy
The example output below shows the 3.9.6 version of Maven installed on the system.

Check the current version of Maven to verify the installation.

