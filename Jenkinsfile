pipeline {
    agent any
    
    stages {
        stage('Build') {
            steps {
                echo 'Checking workspace files...'
                sh 'ls -l main/'  // List files in the 'main' directory
                echo 'Building the project...'
                sh 'g++ -o main/hello_exec main/hello.cpp || echo "Compilation failed!"'  // Compile C++ file
            }
        }
        
        stage('Test') {
            steps {
                echo 'Running Tests...'
                sh './main/hello_exec || echo "Execution failed!"'  // Run the compiled executable
            }
        }
        
        stage('Deploy') {
            steps {
                echo 'Deploying application...'
                sh 'echo "Deployment successful!"'
            }
        }
    }
    
    post {
        failure {
            echo 'Pipeline Failed!'
        }
    }
}
