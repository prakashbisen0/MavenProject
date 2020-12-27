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
   					sh "scp -o StrictHostKeyChecking=no webapp/target/webapp.war ec2-user@15.206.243.230:/root/tomcat/webapps"

						}
                           
                     			 }
				 }
			
			
	          }
          
	}
