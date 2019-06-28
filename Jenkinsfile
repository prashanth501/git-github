pipeline {
    agent any
    stages {
        stage('git clone') {
            steps{
               git credentialsId: 'b0cbdeef-d9e5-4c98-984e-3e3ed7c0c6fc', url: 'https://github.com/prashanth501/spring3hibernate.git'            
            }
        }
		stage('email noti') {
            steps{
               mail bcc: '', body: 'going to deploy', cc: '', from: '', replyTo: '', subject: 'email ', to: 'prashanth.kochu@gmail.com' 
			}
        }
		
		stage('user input'){
		    steps{
			   input id: 'Admin and kochu', message: 'for only and user kochu', submitter: 'kochu'
			 }
	    }
		stage('mvn '){
		    steps{
			   sh 'cd /opt/spring3hibernate/spring3hibernate; mvn deploy'
		     }
		}
	        stage('deploy to tomcat'){
		    steps{
			    sh '/root/.jenkins/workspace/pipeline_test/target /opt/apache-tomcat-8.5.42/webapps'
			}	
        }			 
	}
}

