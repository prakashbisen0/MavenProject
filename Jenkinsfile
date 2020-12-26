pipeline {
 	  agent any
		stages{	
			stage("Maven Build"){
                                 steps{
                           		sh "mvn clean package"
                           
                     			 }
				 }
		stage("deploy-dev"){
           				steps{
		       				sshagent(['tomcat-new']) {
               						sh """
                 					  scp -o StrictHostKeyChecking=no target/webapps.war  ec2-user@15.206.243.230:/opt/tomcat/webapps/
                   
                  					 ssh ec2-user@15.206.243.230 /opt/tomcat/bin/shutdown.sh   
                   
                 					  ssh ec2-user@15.206.243.230 /opt/tomcat/bin/startup.sh
               
               						"""
          						 }
           
         					  }
					}
			
			
	          }
          
	}
