pipeline {
    agent {
        label 'slave4'
    }
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
       stage("tomcat installation") { 
            steps { 
                sh 'rm -rf tomcatfolder'
                sh 'git clone https://github.com/bhaskarshettyhk/tomcatfolder.git'
                 sh "sudo chmod 777 /home/ubuntu/tomcatfolder.sh"
                sh 'sh /home/ubuntu/tomcatinstall.sh'
                echo "tomcat installed"
               }
            }
        stage("deploy") {
            steps { 
               sh 'sudo cp -r $WORKSPACE/target/hello-world-war-1.0.0 /var/lib/tomcat9/webapps'
            }
          }  
       }
}
