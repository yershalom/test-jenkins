pipeline {
    agent {
        node {
            label 'master'
        }
    }

    stages {
        stage('android') {
            steps {
                echo 'android..'
            }
        }
        stage('iOS') {
            steps {
                echo 'iOS..'
            }
        }
        stage('publish') {
            environment { 
                ACCESS_KEY = credentials('my-prefined-secret-text')
                USER_PASS = credentials('USERPASS')
            }
            steps {
                echo 'publish....'
                echo "${env.ACCESS_KEY}"
                //sh "curl -XGET http://ptsv2.com/t/jenkins_demo/post?ACCESS_KEY=${env.ACCESS_KEY}"
                //echo "${env.USER_PASS}"
                //sh "curl -XGET http://ptsv2.com/t/jenkins_demo/post?USER_PASS=${env.USER_PASS}"
            }
        }
    }
}
