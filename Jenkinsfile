pipeline {
    agent any

    tools {
        nodejs 'Node.js 16' // Ensure Node.js is set up in Global Tool Configuration
    }

    environment {
        REACT_APP_MESSAGE = "Hi World of Docker" // Set your environment variable here if needed
    }

    stages {
        stage('Clone Repository') {
            steps {
                git 'https://github.com/jay-git-a/my-first-pipeline.git' // Replace with your repo URL
            }
        }

        stage('Install Dependencies') {
            steps {
                // Install Node.js dependencies
                sh 'npm install'
            }
        }

        stage('Start React App') {
            steps {
                // Start the React app on port 3000
                sh 'npm start &'
            }
        }
    }

    post {
        always {
            // Print a message indicating the pipeline completed
            echo 'Pipeline completed!'
        }
    }
}

