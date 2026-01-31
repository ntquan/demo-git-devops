// Create for me jenkinsfile to run unit test with python in file test_main.py
// including create venvironment and run test
pipeline {
    agent any

    stages {
        stage('Setup Python Environment') {
            steps {
                script {
                    // Create a virtual environment
                    sh 'python3 -m venv venv'
                    // Activate the virtual environment and install dependencies
                    sh '''
                        . venv/bin/activate
                    '''
                }
            }
        }

        stage('Run Unit Tests') {
            steps {
                script {
                    // Activate the virtual environment and run tests
                    sh '''
                        . venv/bin/activate
                        pip install pytest
                        pytest test_baitap1.py -v
                    '''
                }
            }
        }
    }

    post {
        always {
            // Clean up the virtual environment
            sh 'rm -rf venv'
        }
    }
}