# JPET-Jmeter-Scripts
Preconditions:
The idea behind the project is to develop optimal cloud provisioning strategies for the JPetStore application. Ensure the application is
setup and running successfully before running these tests. 

Running JpetStore with Tomcat in Mac:  
 
1. Download and Unzip Tomcat 7  
2. Download the jpetstore source from https://github.com/mybatis/jpetstore-6  
3. From Eclipse, Import -> Maven -> Existing Maven Projects -> select the unzipped jpetstore source  
Delete the following parent pom references from pom.xml file  
```html 
<parent>  
 	<groupId>org.mybatis</groupId>  
<artifactId>mybatis-parent</artifactId>  
<version>26-SNAPSHOT</version>  
 			<relativePath />  
</parent>   
4. Change the version of stripe dependency from 1.6.0 to 1.5.8  
 change “<version>1.6.0</version>” to “<version>1.5.8</version>”  
5. Comment out the two override annotation (@override) from the org.mybatis.jpetstore.web.actions.AbstractActionBean.java file  
6. Right Click the project -> Maven -> Update Project
7. Add Tomcat 7 server to eclipse
8. Eclipse -> Preferences -> Server -> Runtime Environment -> Add -> Select the tomcat7 directory
File -> New -> Other -> Server -> Server -> Apache v7.0 Server
9. Right Click the project -> Run As -> Run Configuration -> Apache Tomcat -> New Configuration -> Add Tomcat 7
10. Right Click the project -> Run As -> Run Configuration -> Maven Build -> New Configuration (Name as JPetStoreWithTomcat7) -> Browse the project as base directory ->  Goals: tomcat7:run -> Run
11. Now jpetstore should be accessible in the browser: http://localhost:8080/jpetstore/
12. To recompile:  Run as -> JPetStoreWithTomcat7
13. Another source version with corrected pom : https://github.com/kenu/jpetstore-6 [Not Tested]

To run the Jmeter scripts:
Run Jmeter GUI, import the .jmx files from the solution

Description:
Cloud.jmx - This contains the testing performed on the cloud. The CLOUDPATH variable value can be modified accordingly to the URL of your cloud account
Local.jmx - This contains the testing performed when the JPetStore is runnin locally on the system

Results: 
In the docs folder the Application Overview.pdf file gives the overall explanation of the project and the findings on the cloud.

