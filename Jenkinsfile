pipeline {
    agent {
        label "slave4"
    }
    environment {
        var = "Build & Deployment"
    }
    stages {
        stage('tomcat installation') {
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
     post{
        always{
            mail to: "krishnamurthyhk57@gmail.com",
            subject: "FAILED",
            body: "deployment is failed "
        }
    }
}
