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
		stage('slack noti'){
		    steps{
			   slackSend iconEmoji: '', message: 'going to start deployment', username: ''
            }
		}
		stage('user input'){
		    steps{
			   input id: 'Admin and kochu', message: 'for only and user kochu', submitter: 'kochu'
			 }
	    }
	}
}
