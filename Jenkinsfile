pipeline {
    agent any
    tools {
        jdk 'JAVA_HOME'
        maven 'M2_HOME'
    }
    stages {
        stage('Checkout GIT') {
            steps {
                echo 'Pulling...'
                // Fetch the code from the specified Git repository
                git branch: 'master', url: 'https://github.com/borisdylan/Final-Spring.git'
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
