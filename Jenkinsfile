pipeline {
    agent any
    tools {
        maven 'M2_HOME'
        jdk 'JAVA_HOME'
        
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
                sh 'mvn clean install -DskipTests'
            }
        }
        stage('MVN SONARQUBE') {
            steps {
                // Run 'mvn compile' command
                sh 'mvn sonar:sonar -Dsonar.login=sonar'
            }
        }

    }
}
