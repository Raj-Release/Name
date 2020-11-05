pipeline {
	agent { 
	  label 'Linux'
	}
	options{ 
	  timestamps()
	}
	stages {
             stage ('Checkout source code')
    {
	  steps{
	      git credentialsId: 'f93634d9-d19e-4361-a4d9-aebfd7d2edac', url: 'https://github.com/Raj-Release/Name.git'
      }
     }
	 stage('Build') {
            steps {
                sh 'mvn clean install'
            }
        }
    }
}
	
