pipeline {
    agent any

    stages {
        stage('Build') {
            environment { 
                ACCESS_KEY = credentials('my-prefined-secret-text') 
            }
            steps {
                echo 'Building..'
                echo ${env.ACCESS_KEY}
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}
