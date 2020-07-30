pipeline {
    agent { label 'dockerserver' }
    stages {
        stage('Back-end') {
            agent {
                label 'dockerserver'
                docker { image 'maven:3-alpine' }
            }
            steps {
                sh 'mvn --version'
            }
        }
        stage('Front-end') {
            agent {
                label 'dockerserver'
                docker { image 'node:14-alpine' }
            }
            steps {
                sh 'node --version'
            }
        }
    }
}
