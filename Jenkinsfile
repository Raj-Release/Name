pipeline {
	agent { label 'Linux'}
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
	stage('Nexus artifact upload') {
            steps {
                nexusArtifactUploader (
               artifacts: [[artifactId: 'helloworld', 
			   classifier: '', 
			   file: 'target/helloworld-1.1.jar', 
			   type: 'jar']], 
			   credentialsId: '37413181-35c0-4210-ab3b-ceecaac947c4', 
			   groupId: 'com.coveros.demo', 
			   nexusUrl: '3.6.217.3:8081', 
			   nexusVersion: 'nexus3', 
			   protocol: 'http', 
			   repository: 'Test', 
			   version: '1.1'
			   )
            }
        }
		
    }
	
}
