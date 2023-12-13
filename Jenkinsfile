pipeline {
    agent any
    stages{
            stage('Checkout GIT'){
                steps{

                    echo 'Pulling...';
                    git branch: 'main',
                    url : 'https://github.com/borisdylan/5WIN-G1-EventsProject.git'
                }
            }
            stage('Testing maven'){
                steps {
                    sh """mvn -version"""
                }
            }
    }
}