@Library('my-shared-lib') _

pipeline {
    agent any

    tools {
        maven 'maven'
        jdk 'jdk21'
    }

    stages {

        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Build') {
            steps {
                script {
                    mavenBuild()
                }
            }
        }

        stage('Docker Build') {
            steps {
                script {
                    dockerBuild()
                }
            }
        }

    }
    post {

        success {
            echo 'Pipeline Executed Successfully'
        }

        failure {
            echo 'Pipeline Failed'
        }
    }
}
