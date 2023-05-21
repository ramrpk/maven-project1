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
        stage("deploy"){
            steps{
                sshagent(['tomcat']) {
                  sh "scp -o StrictHostKeyChecking=no /target/devops91.war  ec2-user@13.235.2.224:/home/ec2-user/apache-tomcat-9.0.75/webapps"
                                 
                }
            }
         }
    }
}
