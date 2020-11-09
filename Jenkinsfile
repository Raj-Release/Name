


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
                sh 'mvn clean package'
            }
        }
	stage('Upload war file into nexus')
	  steps{ 
	    nexusArtifactUploader ( artifacts: [[artifactId: 'helloworld', 
                      classifier: '', 
					  file: 'target/helloworld-1.4.jar', 
					  type: 'jar']], 
                      credentialsId: '409761be-c2e9-423a-a795-b8000c04104b',
                      groupId: 'com.coveros.demo', 
                      nexusUrl: '15.207.106.201:8081', 
                      nexusVersion: 'nexus3', 
                      protocol: 'http', 
                      repository: 'Sample_both', 
                      version: '1.4'
					  )
		  
    }
 }
}

