pipeline {
    agent any
    
    stages {
        stage('Build') {
            steps {
                script {
                    // Compile the .cpp file using shell script
                    sh 'g++ -o hello hello.cpp'
                }
            }
        }
        
        stage('Test') {
            steps {
                script {
                    // Print output of .cpp file using shell script
                    sh './hello'
                }
            }
        }
        
        stage('Deploy') {
            steps {
                script {
                    // Add deployment steps here if needed
                }
            }
        }
    }
    
    post {
        always {
            script {
                // Display 'pipeline failed' in case of any errors within the pipeline
                currentBuild.result = currentBuild.result ?: 'SUCCESS'
                if (currentBuild.result == 'FAILURE') {
                    echo 'pipeline failed'
                }
            }
        }
    }
}
