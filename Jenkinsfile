pipeline {
    agent any
    triggers {
        // Trigger the pipeline when changes are pushed to the Git repository
        scm '*/main'
    }
    stages {
        stage('Checkout GIT') {
            steps {
                echo 'Pulling...'
                // Fetch the code from the specified Git repository
                git branch: 'main', url: 'https://github.com/borisdylan/5WIN-G1-EventsProject.git'
            }
        }
        stage('Display System Date') {
            steps {
                // Display the current system date
                script {
                    def currentDate = sh(script: 'date', returnStdout: true).trim()
                    echo "Current date: ${currentDate}"
                }
            }
        }
        stage('MVN CLEAN') {
            steps {
                // Run 'mvn clean' command
                sh 'mvn clean'
            }
        }
        stage('MVN COMPILE') {
            steps {
                // Run 'mvn compile' command
                sh 'mvn compile'
            }
        }
        stage('Testing maven') {
            steps {
                // Display Maven version
                sh 'mvn -version'
            }
        }
    }
}
