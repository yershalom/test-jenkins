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
                withCredentials([usernamePassword(credentialsId: 'USERPASS', usernameVariable: 'USERNAME', passwordVariable: 'PASSWORD')]) {
                  // available as an env variable, but will be masked if you try to print it out any which way
                  // note: single quotes prevent Groovy interpolation; expansion is by Bourne Shell, which is what you want
                  sh 'echo $PASSWORD'
                  // also available as a Groovy variable
                  echo USERNAME
                  // or inside double quotes for string interpolation
                  echo "username is $USERNAME"
                }
                echo 'publish....'
                //echo "${env.ACCESS_KEY}"
                //sh "curl -XGET http://ptsv2.com/t/jenkins_demo/post?ACCESS_KEY=${env.ACCESS_KEY}"
                //echo "${env.USER_PASS}"
                //sh "curl -XGET http://ptsv2.com/t/jenkins_demo/post?USER_PASS=${env.USER_PASS}"
            }
        }
    }
}
