#!/usr/bin/env groovy
pipeline {
    agent any

    environment {
        language = 'PHP'
    }

    stages {
        stage('Build') {
            steps {
                echo 'Building'
            }
        }
        stage('Tests') {
            steps {
                echo 'Testing'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
        stage('Example'){
            steps {
                echo "Running ${env.BUILD_ID} on ${env.JENKINS_URL}"
            }
        }
        stage('Env') {
            steps {
                sh 'printenv'
            }
        }
    }
}