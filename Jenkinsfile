pipeline {
    agent any
    
    parameters {
        string(name: 'VERSION', defaultValue: '', description: 'Version to deploy on prod')
        choice(name: 'VERSION', choices: ['1.1.0', '1.2.0', '1.3.0'], description: 'Select version')
        booleanParam(name: 'executeTests', defaultValue: true, description: 'Run Test Stage')
    }
    
    environment {
        NEW_VERSION = '1.3.0'
    }

    stages {
        stage('Build') {
            steps {
                echo 'Building Project'
                // Build steps go here
            }
        }
        
        stage('Test') {
            when {
                expression {
                    return params.executeTests
                }
            }
            steps {
                echo 'Testing Project'
                // Test steps go here
            }
        }
        
        stage('Deploy') {
            steps {
                echo "Deploying version ${params.VERSION ?: NEW_VERSION}"
                // Deploy steps go here
            }
        }
    }
    
    post {
        always {
            echo 'Post building condition running'
        }
        failure {
            echo 'Post action if build failed'
        }
    }
}
