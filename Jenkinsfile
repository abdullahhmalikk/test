// Define the flag variable at the top of the Jenkinsfile
def flag = true

pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo 'Building..'
                // Here you can define commands for your build
            }
        }
        stage('Test') {
            when {
                expression {
                    return flag == true
                }
            }
            steps {
                echo 'Testing..'
                // Here you can define commands for your tests
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
                // Here you can define commands for your deployment
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
