# Develop-on-ECS
take down the experience of start up a webset (from purchase Domain Name||cloud servers) 

***
# Directory  
 :book:   
* [Domain-name](#domain-name)  
* [Cloud-server-ECS](#Cloud-server-ECS)  
* [Configure-CentOS-environment](#Configure-CentOS-environmen)  
   * [install-mysql-server](#install-mysql-server)  
   * [install-JDk](#install-JDk)  
   * [install-tomcat](#install-tomcat)
  
  
  
## Domain-name
ur webset do need a name to access,this name was called Domain name  
i purchase Domain name on [GoDaddy](https://sg.godaddy.com/)
  
1. sign up and login in GoDaddy 
  
2. click the donmain buttom and search the donmain name ,make sure it's for sell 
  
3. chose the one u want and buy it ,normally it cost 20 RMB 
  
4. complete the necessary information
  
## Cloud-server-ECS
Everey webset need a server,u can build your server by yourself but it's expensive and difficult  
at present , lot of organization and co chose cloud server.it was provide by the network operators   
network operators will ensure the security of your webset  
    
i chose ali to buy a ECS [阿里云](https://www.aliyun.com/)  
    
if your are a student you can have the discount [云翼计划](https://promotion.aliyun.com/ntms/act/campus2018.html)  
we select the ecs and buy  
![](https://github.com/JaseGoo/Develop-on-ECS/raw/master/img/2019-07-12_150739.png)
  
**use centos 7 system ,it's widely use around the world**

  
## Configure-CentOS-environment  
1. PuTTY was needed to access your server **u can download PuTTY in this poject**  
2. use your public ip (you can check it on your ECS consol) to log in  
![](https://github.com/JaseGoo/Develop-on-ECS/raw/master/img/2019-07-12_163405.png)  
log as:root
password:(u set on ECS)  
### install-mysql-server
    1.download   
wget http://dev.mysql.com/get/Downloads/MySQL-5.6/MySQL-5.6.22-1.el6.i686.rpm-bundle.tar  

    2. decompression to /usr/local/mysql

tar -xvf MySQL-5.6.22-1.el6.i686.rpm-bundle.tar  

    3. install Mysql_Server 

            1. install ： yum -y install libaio.so.1 libgcc_s.so.1libstdc++.so.6 

            2. update libstdc  

                    yum update libstdc++-4.8.5-11.el7.x86_64  

                    yum update libgcc-4.8.5-11.el7.x86_64  

            3. install mysql_server   
            
                    rpm -ivh MySQL-server-5.6.22-1.el6.i686.rpm  

### install-JDk 
1. download jdk-7u55-linux-i586.tar.gz    
http://www.oracle.com/technetwork/java/javase/downloads/java-archive-downloads-javase7-521261.html#jdk-7u55-oth-JPR
  
2. find the install file of your PuTTY ,use cmd to upload JDK file  
  pscp file path+file name @ public ip:/home/(location you want)  
  input your centos password  
  
3. install glibc   
yum install glibc.i686  
  
4. configure environment     
vi/etc/profile
  add  
  #setjava environment
    
        JAVA_HOME=/usr/local/java/jdk1.7.0_71

        CLASSPATH=.:$JAVA_HOME/lib.tools.jar  
        
        PATH=$JAVA_HOME/bin:$PATH

        exportJAVA_HOME CLASSPATH PATH

        source/etc/profile  

        java -version  
          
          
            
### install-tomcat  
 1. upload jdk-7u72-linux-i586.gz to server
 
 2. decompression to  /usr/local/   tar -xzf jdk-7u72-linux-i586.gz

 3. put your project under webapps

 4. use bin/strartup.sh to start tomcat server

 5. access http://ip:8080/   

                  
