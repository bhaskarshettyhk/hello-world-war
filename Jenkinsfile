pipeline {
    agent none
      stages {
        stage("checkout") { 
            agent {
             label 'slave1'
            }   
            steps {
                sh 'rm -rf hello-world-war'
                sh 'git clone https://github.com/bhaskarshettyhk/hello-world-war.git'
            }
        }
       stage("build") { 
           agent {
            label 'slave1'
           }   
            steps { 
                sh 'mvn package'
               }
            }
        stage("deploy") {
            agent {
              label 'slave2'  
            steps { 
              sh 'sudo cp -r $WORKSPACE/target/hello-world-war-1.0.0 /var/lib/tomcat9/webapps'
            }
          }  
       }
     }
