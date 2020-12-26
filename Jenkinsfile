pipeline {
 	  agent any
		stages{	
			stage("Maven Build"){
                                 steps{
                           		sh "mvn clean package"
                           		sh "mv target/*.war target/myweb.war"
                     			 }
				 }
		stage("deploy-dev"){
           				steps{
		       				sshagent(['tomcat-new']) {
               						sh """
                 					  scp -o StrictHostKeyChecking=no target/myweb.war  ec2-user@15.206.243.230:/opt/tomcat/webapps/
                   
                  					 ssh ec2-user@15.206.243.230 /opt/tomcat/bin/shutdown.sh   
                   
                 					  ssh ec2-user@15.206.243.230 /opt/tomcat/bin/startup.sh
               
               						"""
          						 }
           
         					  }
					}
			
			
	          }
          
	}
