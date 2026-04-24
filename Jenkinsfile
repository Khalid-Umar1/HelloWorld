pipeline {
    agent any
    environment {
        VERSION = '1.0.0'
    }
    parameters {
        booleanParam(name: 'executeTests', defaultValue: true, description: 'Run the Test stage?')
    }
    stages {
        stage('Build') {
            steps {
                echo 'Building..'
                echo "Building version ${VERSION}"
            }
        }
        stage('Test') {
            when {
                expression {
                    params.executeTests == true
                }
            }
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
    post {
        always {
            echo 'This always runs after the pipeline!'
        }
        success {
            echo 'Pipeline succeeded!'
        }
    }
}
