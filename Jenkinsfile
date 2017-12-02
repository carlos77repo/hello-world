#!groovy

import groovy.json.JsonSlurper
import java.net.URL

pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building..'
                javac HelloWorld.java
            }
        }
        stage('Test') {
            steps {
                echo 'Testing...'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
    post {
        always {
          step([$class: 'Mailer',
            notifyEveryUnstableBuild: true,
            recipients: "thvnbx@aol.com",
            sendToIndividuals: true])
        }
      }
}
