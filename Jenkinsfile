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
                sh 'sudo cp /var/lib/jenkins/workspace/multibranchtrail_develop/target/hello-world-war1.0.0.war /var/lib/tomcat9/webapps'   
	         }
        } 
    }
}
