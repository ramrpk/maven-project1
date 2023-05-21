pipeline {
    agent any
    stages {
        stage('clone') {
            steps {
                // Get some code from a GitHub repository
                git url: 'https://github.com/ramrpk/maven-project1.git', branch: 'master'

            }
        }
        stage('Build') {
            steps {
                sh 'mvn -Dmaven.test.failure.ignore=true install'
      
            }
        }
        stage("deploy-dev"){
            steps{
                sshagent(['tomcat-dev1']) {
                 sh """
                 scp -o StrictHostKeyChecking=no target/devops91.war  
                 ec2-user@http://13.235.2.224:8080/ :/opt/tomcat/webapps/
                 ssh ec2-user@http://13.235.2.224:8080/ /opt/tomcat/bin/shutdown.sh
                 ssh ec2-user@http://13.235.2.224:8080/ /opt/tomcat/bin/startup.sh
                 """
                }
            }
         }
    }
}
