pipeline {
    agent any

    parameters {
        string(name: 'BRANCH_NAME', defaultValue: 'master', description: 'Enter the branch name')
    }

    stages {
        stage('Checkout') {
            steps {
                // Checkout the specified branch from the GitHub repository
                checkout([$class: 'GitSCM',
                          branches: [[name: "${params.BRANCH_NAME}"]],
                          userRemoteConfigs: [[
                              url: 'https://github.com/your-username/your-repo.git',
                              credentialsId: 'your-credentials-id'
                          ]]
                ])
            }
        }

        // Add more stages for your pipeline
        // ...
    }
}
