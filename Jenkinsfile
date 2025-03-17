pipeline {
    agent any  // Runs on any available Jenkins agent

    stages {
        stage('Build') {
            steps {
                script {
                    echo 'Building the C++ program...'
                    sh 'g++ -o hello_exec main/hello.cpp'  // Compile hello.cpp
                }
            }
        }

        stage('Test') {
            steps {
                script {
                    echo 'Running the compiled program...'
                    sh './non_existent_binary'  // Intentional error to make this stage fail
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
            echo 'Pipeline failed! Please check errors.'  // Failure handling message
        }
    }
}
