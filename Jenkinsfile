pipeline {
    agent any  // Runs on any available Jenkins agent

    stages {
        stage('Build') {
            steps {
                script {
                    echo 'Building the C++ program...'
                    sh 'g++ -o hello_exec main/hello.cpp'  // Compiles hello.cpp
                }
            }
        }

        stage('Test') {
            steps {
                script {
                    echo 'Running the compiled program...'
                    sh './hello_exec'  // Executes the compiled binary
                }
            }
        }

        stage('Deploy') {
            steps {
                script {
                    echo 'Deploying the application...'
                    sh 'echo "Deployment successful!"'
                }
            }
        }
    }

    post {
        failure {
            echo 'Pipeline failed! Please check errors.'
        }
    }
}
