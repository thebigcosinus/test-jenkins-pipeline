#!/usr/bin/env groovy
pipeline {
    agent {
        docker {image 'node:7-alpine'}
    }

    environment {
        language = 'PHP'
    }

    parameters {
        string(name: 'Greeting', defaultValue: 'Hello', description: 'How should I greet the world?')
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
        stage('Parameters') {
            steps {
                echo  "${params.Greeting}"
            }
        }
        post {
            always {
                junit '**/target/*.xml'
            }
            failure {
                mail to: team@example.com, subject: 'The Pipeline failed :('
            }
        }
        stage('Docker') {

            steps {
                sh 'node --version'
            }
        }
    }
}