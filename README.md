WeatherWebApplicaion
====================


Web Application for displaying United States City's Temperature(F) Using ZipCode

Please follow below steps to setup and deploy the web application.

# Environmental Setup
   (Ignore if you already have all java setup on your machine)
   Before starting build/deploy of application make sure you have below setup on your machine.

-   JDK 1.7 or above: 
    If you don't have Jave Development Kit installed on your machine please use below link to install. 
    http://www.oracle.com/technetwork/java/javase/downloads/jdk7-downloads-1880260.html

-   Eclipse IDE:
    Install any of the eclipse versions from below link.
    http://www.eclipse.org/downloads/packages/eclipse-standard-44/lunar

-   Apache Tomcat Server 7 in eclipse:
    Windows -> Show View -> Servers to view server tab
    Click on create a server link
    Select Apache - Tomcat 7.0 or above server and click Next
    Select Tomcat directory ex. 'D:\Java\Tomcat 7\apache-tomcat-7.0.53' (If don't have please install from apache site)
    Select JRE as jdk1.7.0_xx and click Finish

-   Change Installed JRE in eclipse:
    Go to below eclipse path and setup JDK as Installed JRE in eclipse.
    Windows -> Preferences -> Java -> Installed JREs -> Add -> Standard VM -> Directory
    select JDK installed path ex. C:\Program Files\Java\jdk1.7.0_67
    Now select jdk1.7.0_xx as Installed JRE.
    
-   Install Git into Eclipse:
    Go to Help > Install new software in eclipse
    Type work with: http://download.eclipse.org/egit/updates 
    Select 'Eclipse Git Team Provider' and click Next, Finish
    This will install Git plugin into eclipse so you can directly import git project into eclipse.
    Also install GitHub in you local machine from github.com



Now we have everything setup so we are ready to Deploy/ Test/ Run.

# Import the application from Gits
-   File -> Import -> Projects from Git -> Next -> Clone URI
-   Give URI: https://github.com/swapnilsuhane/WeatherApplication
-   protocol: 'https' then give user/password -> Next
-   Select master -> Next
-   Give the directory you want to import the project into local machine ex. C:\Users\swapnil_suhane\git\WeatherApplication > Next
-   Select Import Existing projects > Next
-   Select WeatherApp > Finish
-   This will now import the gits repo project into your local eclipse.
-   Note: Make sure you change eclipse Installed JRE to JDK as mentioned above. Othewise it will give errors while deployment.

# Build/Test Maven Project
-   Right click on WeatherApp project in the eclipse and goto Run As -> Maven build
-   Goals- clean install
-   Click Run. It will build the maven project along with running all Junit Tests.
-   You should get 'BUILD SUCCESS' if no errors reported.
-   Also check the JUnit results ex.
Results :
Tests run: 15, Failures: 0, Errors: 0, Skipped: 0

# Running Maven application on Tomcat Server in eclipse
-   Before running application on server please add maven jar dependency in eclipse else you will get error.
-   Right click on WeatherApp project in the eclipse Properties -> Deployment Assembly -> Add -> Java Build Path Entries
-   Select 'Maven Dependencies' then click OK/Finish. It will add dependent jar path in eclipse. 
-   Now Right click on WeatherApp project in the eclipse and goto Run As -> Run on Server
-   Choose 'Manually define a new server' option. Select Apache > 'Tomcat v7.0  Server' > click Next.
-    Select Tomcat directory ex. 'D:\Java\Tomcat 7\apache-tomcat-7.0.53' where your tomcat exist in your local machine. (If don't have please install from apache site)
    Select JRE as jdk1.7.0_xx and click Finish
-   Now we are good to start tomcat server. Right click on server and start it.
-   If you see any error while starting tomcat server please check the console logs and check you have all environmental setup on eclipse as mentioned above. 
-   Check the application is running using URL: http://localhost:8080/WeatherApp/


# Check the Weather Application URL: http://localhost:8080/WeatherApp/
-    You will see the web page to enter ZipCode (valid 5 length + numeric)
-    Upon clicking Submit same page will display you City, State, Temperature in Fahrenheit.
-    If you don't enter any zipcode you will get a validation message 'ZipCode is required'
-    If you enter any invalid zipcode (ex. 100) you will get validation message 'Invalid ZipCode Format'
-    If you enter any valid zipcode that does not exist (ex. 10000) you will get a javascript validation message 'ZipCode Not Found !!'


# Import application using WeatherApp.war
-   You can also import the war file directly to deploy into tomcat and run the webApp.
-   Import the project using war file with below eclipse path.
    File -> Import -> War File -> Browse
-   Now select the war file path in your machine. (save local if you haven't)
-   Click finish (no need to select jars)


# Running Junit Test on Eclipse
-   Right click on WeatherApp project in the eclipse and goto Run As -> Junit Test
-   In the Junit tab you will see Green bar along with test counts if all tests are successful.
