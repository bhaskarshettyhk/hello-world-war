pipeline {
    agent none
      stages {
        stage("checkout") { 
            agent {
                label 'slave4'
            }
            steps {
                sh 'rm -rf hello-world-war'
                sh 'git clone https://github.com/bhaskarshettyhk/hello-world-war.git'
            }
        }
       stage("build") { 
           agent {
               label 'slave4'
            }
            steps { 
                sh 'mvn package'
               }
            }
        stage("deploy") {
            agent {
                label 'slave4'
            }
            steps { 
             echo "hi"   
             // sh 'sudo cp -r $WORKSPACE/target/hello-world-war-1.0.0 /var/lib/tomcat9/webapps'//
            }
          }  
       }
         post{
        always{
            mail to: "krishnamurthyhk57@gmail.com",
            subject: "Test Email",
            body: "Test"
        }
    }
}
