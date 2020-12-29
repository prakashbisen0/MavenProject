pipeline {
 	  agent any
		stages{	
			stage("Maven Build"){
                                 steps{
                           		sh "mvn clean package"
                           
                     			 }
				 }
			
			stage("Deploye"){
                                 steps{
                           		sshagent(['deploye_user']) {
   					sh "scp -o StrictHostKeyChecking=no webapp/target/webapp.war root@15.206.243.230:/home/root/tomcat/webapps"

						}
                           
                     			 }
				 }
			
			
	          }
          
	}
