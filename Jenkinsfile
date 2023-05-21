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
                sh 'mvn clean install'
            }
        }
    }
}
