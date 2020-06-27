1 # Install_Jenkins


To install Jenkins on your CentOS system, follow the steps below:
Jenkins is a Java application, so the first step is to install Java. Run the following command to install the OpenJDK 8 package:

$ sudo yum install java-1.8.0-openjdk-devel



2 # Enable the Jenkins repository. To do that, import the GPG key using the following curl command:

    $ curl --silent --location http://pkg.jenkins-ci.org/redhat-stable/jenkins.repo | sudo tee /etc/yum.repos.d/jenkins.repo
  
3 # And add the repository to your system with:
  
    $ rpm --import https://jenkins-ci.org/redhat/jenkins-ci.org.key
    
4 # Once the repository is enabled, install the latest stable version of Jenkins by typing

    $ yum install jenkins
    
5 # After the installation process is completed, start the Jenkins service with

    $ systemctl start jenkins
    
6 # To check whether it started successfully run:
    $ systemctl status jenkins
    
7 # Finally enable the Jenkins service to start on system boot.
    
    $ systemctl enable jenkins
    
    
    OutPut: jenkins.service is not a native service, redirecting to /sbin/chkconfig.
    Executing /sbin/chkconfig jenkins on
    
    
8 # Adjust the Firewall 

    If you are installing Jenkins on a remote CentOS server that is protected by a firewall you need to port 8080.
    
    $ sudo firewall-cmd --permanent --zone=public --add-port=8080/tcp
    $  sudo firewall-cmd --reload  
    
9 # Setting Up Jenkins 

    set up your new Jenkins installation, open your browser and type your domain or IP address followed by port 8080:

10 # following command to print the password on your terminal

    $ sudo cat /var/lib/jenkins/secrets/initialAdminPassword
    
11 # Copy the password from your terminal, paste it into the Administrator password field and click Continue.

