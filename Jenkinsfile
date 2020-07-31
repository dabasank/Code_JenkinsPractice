@Library('TestLibrary')_

pipeline {
    agent any 
    environment {
        // Using returnStdout
        CC = """${sh(
                returnStdout: true,
                script: 'echo "clang"'
            )}""" 
        // Using returnStatus
        EXIT_STATUS = """${sh(
                returnStatus: true,
                script: 'exit 1'
            )}"""
    }
    stages {
     stage('Demo_Shared_Library') {
         steps {
          echo "Hello world"
          firstVariable
     }
     }
     
     stage('Example') {
            environment {
                DEBUG_FLAGS = '-g'
     }
            steps {
                sh 'printenv'
                echo "printenv"
                //echo "$printenv"
                
                echo "Value of CC is ${env.CC.trim()}"
                echo "Value of EXIT_STATUS is ${env.EXIT_STATUS}"
                
                //Printing Environment Variables
                echo "Running ${env.BUILD_ID} on ${env.JENKINS_URL} and with ${NODE_NAME} node"
                echo "Running ${env.BUILD_ID} on ${env.EXECUTOR_NUMBER}"
                echo "Workspace is ${env.WORKSPACE}"
            }
        }
    }
}
