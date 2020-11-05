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
	      git credentialsId: 'c1decb44-5c03-42fa-80d2-6f37e387d279', url: 'https://github.com/Raj-Release/Name.git'
      }
     }
	 stage('Build') {
            steps {
                sh 'mvn -Dmaven.test.failure.ignore=true install'
            }
        }
    }
}
