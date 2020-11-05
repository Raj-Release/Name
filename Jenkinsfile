pipeline {
	agent { 
	  label 'Linux'
	}
	tools { 
        maven 'Maven 3.6.3' 
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
                sh 'mvn -Dmaven.test.failure.ignore=true install'
            }
        }
    }
}
