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
			     sh 'cd /opt/spring3hibernate/spring3hibernate; mvn package'
		     }
		}
	        stage('deploy to tomcat'){
		    steps{
			    sh 'cp /opt/spring3hibernate/spring3hibernate/target/*.war /opt/apache-tomcat-8.5.42/webapps'
			}	
        }			 
	}
}
	post {  
         success {  
             echo 'This will run only if successful'  
         }  
         failure {  
             mail bcc: '', body: "<b>Example</b><br>Project: ${env.JOB_NAME} <br>Build Number: ${env.BUILD_NUMBER} <br> URL de build: ${env.BUILD_URL}", cc: '', charset: 'UTF-8', from: '', mimeType: 'text/html', replyTo: '', subject: "ERROR CI: Project name -> ${env.JOB_NAME}", to: "prashanth.kochu@gmail.com";  
         }  
         unstable {  
             echo 'This will run only if the run was marked as unstable'  
         }  
         
      }
