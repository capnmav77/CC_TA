pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                script {
                    sh 'g++ -o output main.cpp'  // Compile the C++ file
                }
            }
        }

        stage('Test') {
            steps {
                script {
                    sh './output'  // Run the compiled file
                }
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying application...'
            }
        }
    }

    post {
        failure {
            echo 'Pipeline failed! ❌'
        }
        success {
            echo 'Pipeline completed successfully! ✅'
        }
    }
}
