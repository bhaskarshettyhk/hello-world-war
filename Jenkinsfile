pipeline {
    agent {
        label "slave4"
    }
    environment {
        var = "Build & Deployment"
    }
    stages {
        stage('checkout') {
            steps {
                sh 'rm -rf hello-world-war'
                sh 'git clone https://github.com/bhaskarshettyhk/hello-world-war.git'
                sh 'chmod 755 ${WORKSPACE}/hello-world-war/tomcatscript'
                sh '${WORKSPACE}/hello-world-war/tomcatscript'
            }
        }
        stage('build') {
            steps {
                dir('hello-world-war') {
                    sh 'mvn package'
                }
            }
        }
        stage('deploy step') {
            steps {
                build job: 'email'
                echo "the whole $var is success"
            }
        }
    }
   stage('Send Email') {
    steps {
        script {
            emailext subject: 'Build Status',
                body: 'The build is complete.',
                to: 'krishnamurthyhk57@gmail',
                mimeType: 'text/plain',
                replyTo: 'bhaskarshettyd@gmail.com'
        }
    }
} 
}

