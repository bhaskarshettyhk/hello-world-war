pipeline {
    agent any
    stages {
        stage("checkout") { 
            steps {
                sh 'rm -rf hello-world-war'
                sh 'git clone https://github.com/bhaskarshettyhk/hello-world-war.git'
            }
        }
       stage("build") { 
            steps { 
                sh 'mvn package'
               }
            }
        stage("build") { 
            steps { 
              sh 'sudo cp -r $WORKSPACE/target/hello-world-war-1.0.0 /var/lib/tomcat9/webapps
            }
          }  
       }
     }
