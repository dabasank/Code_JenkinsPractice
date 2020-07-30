pipeline {
    agent { label 'dockerserver' }
    stages {
        stage('Back-end') {
            agent {
                docker { 
                    label 'dockerserver'
                    image 'maven:3-alpine' 
                }
            }
            steps {
                sh 'mvn --version'
            }
        }
        stage('Front-end') {
            agent {
                docker { 
                    label 'dockerserver'
                    image 'node:14-alpine' 
                }
            }
            steps {
                sh 'node --version'
            }
        }
    }
}
