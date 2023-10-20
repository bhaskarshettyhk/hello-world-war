pipeline {
    agent {
        label 'slave5'
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
                sh 'sh tomcatinstall.sh'
                echo "tomcat installed"
               }
            }
        stage("deploy") {
            steps { 
               sh 'sudo cp -r /home/ubuntu/workspace/tomcatinstallonslave@2/hello-world-war/target/hello-world-war-1.0.0 /var/lib/tomcat9/webapps'
            }
          }  
       }
}
