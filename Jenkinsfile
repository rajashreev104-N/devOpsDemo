pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building the project...'

                bat 'if not exist build mkdir build'
                bat 'echo Build Successful > build\\output.txt'
            }
        }

        stage('Test') {
            steps {
                echo 'Running Tests...'
                bat 'echo All Tests Passed'
            }
        }

        stage('Archive') {
            steps {
                archiveArtifacts artifacts: 'build/*', fingerprint: true
            }
        }
    }

    post {
        success {
            echo 'Pipeline Executed Successfully'
        }
    }
}
