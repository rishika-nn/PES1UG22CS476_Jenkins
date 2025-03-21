pipeline {
    agent any
    
    stages {
        stage('Build') {
            steps {
                echo 'Building the project...'
                sh 'g++ -o hello_exec hello.cpp'  // Compile the C++ file
            }
        }
        
        stage('Test') {
            steps {
                echo 'Running Tests...'
                sh './hello_exec'  // Run the compiled executable
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
