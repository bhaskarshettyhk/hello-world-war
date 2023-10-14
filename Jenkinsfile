pipeline {
    agent any
    stages {
        stage('checkout') {
            steps {	
                sh 'git clone https://github.com/bhaskarshettyhk/hello-world-war/'
            }
        }

	    stage('Build') {
            steps {		
                sh 'mvn clean package'
            }
        }   
    }
}
