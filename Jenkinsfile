pipeline {
	agent { label 'Linux'}
	tools {
		maven 'apache-maven-3.6.3'
	}

    stages {
        stage('SCM Checkout') {
            steps {
                git credentialsId: 'f93634d9-d19e-4361-a4d9-aebfd7d2edac', url: 'https://github.com/Raj-Release/Name.git'
            }
        }
        stage('Build') {
            steps {
                sh 'mvn clean verify'
            }
        }
		
    }
	
}
