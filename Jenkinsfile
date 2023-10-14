pipeline {
    agent any
    stages {
        stage('checkout') {
            steps {	
		    sh 'rm -rf hello-world-war'
                sh 'git clone https://github.com/bhaskarshettyhk/hello-world-war/'
            }
        }
	stage('Build') {
            steps {		
                sh 'mvn clean package'
            }
        } 
	 stage('Deploy') {
            steps {		
                sh 'sudo cp /var/lib/jenkins/workspace/multibranchtrail_develop/target/hello-world-war-1.0.0 /var/lib/tomcat9/webapps'   
	         }
        } 
    }
}
