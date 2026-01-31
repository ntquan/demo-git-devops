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
                        source venv/bin/activate
                        pip install -r requirements.txt
                    '''
                }
            }
        }

        stage('Run Unit Tests') {
            steps {
                script {
                    // Activate the virtual environment and run tests
                    sh '''
                        source venv/bin/activate
                        python -m unittest discover -s tests -p "test_main.py"
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