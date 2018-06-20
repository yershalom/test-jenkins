pipeline {
    agent any

    stages {
        stage('Build') {
            environment { 
                ACCESS_KEY = credentials('my-prefined-secret-text')
                USER_PASS = credentials('USERPASS')
            }
            steps {
                echo 'Building..'
                echo "${env.ACCESS_KEY}"
                echo "${env.USER_PASS}"
                sh "curl -XGET http://ptsv2.com/t/jenkins_demo/post?ACCESS_KEY=${env.ACCESS_KEY}"
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
