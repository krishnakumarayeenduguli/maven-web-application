/* 	node{
    properties([buildDiscarder(logRotator(artifactDaysToKeepStr: '', artifactNumToKeepStr: '5', daysToKeepStr: '', numToKeepStr: '5')), [$class: 'JobLocalConfiguration', changeReasonComment: ''], pipelineTriggers([pollSCM('* * * * *')])])
    
	def mavenHome = tool name: 'maven_3.9.6'
    
	echo "Build Number is: ${env.BUILD_NUMBER}"
	echo "Job name is: ${env.JOB_NAME}"
	echo "Node name is: ${env.NODE_NAME}"
	echo "jenkins home directory is: ${env.JENKINS_HOME}"
    echo "build URL is: ${env.BUILD_URL}"
	echo "build URL is: ${env.BUILD_URL}"
	echo "jenkins URL is: ${env.JENKINS_URL}"
	
			              stage('CheckOutCode'){
				                git branch: 'development', credentialsId: '05bf05c8-618a-4a63-9023-141178b39ee9', url: 'https://github.com/krishnakumarayeenduguli/maven-web-application.git'
							  }
			              stage('Build')
			                  {
			                    sh "${mavenHome}/bin/mvn clean package"
                    		  }

  
			             stage('ExcuteSonarQubeReport')
							  {
							    sh "${mavenHome}/bin/mvn clean sonar:sonar"
							  }
						  stage('UploadArtifactsInToNexus')	
							  {
							    sh "${mavenHome}/bin/mvn clean deploy"
							  }
						   stage('DeployAppIntoTomcat')
							  {
    							sshagent(['93e83c56-0fa2-43a9-ad5c-289df6f7403e']) 
    							    {
    								    sh "scp -o StrictHostKeyChecking=no target/maven-web-application.war ec2-user@172.31.45.118:/opt/apache-tomcat-9.0.83/webapps"
    								}
							  }
         */
		
		}
