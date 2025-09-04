pipeline {
    agent any
    
    environment {  // creating environment variables
        MY_NAME = "Ayush"
        PROJECT = "DevOps-Assignment"
    }
    
    parameters {   // parameters
        string(name: 'MY_NAME1', defaultValue: 'Ayush', description: 'Enter your name')
        string(name: 'PROJECT1', defaultValue: 'DevOps-Assignment', description: 'Enter project name')
        choice(name: 'ENVIRONMENT', choices: ['DEV', 'QA', 'PROD'], description: 'Select environment')
    }

    stages {
        stage('Test') {
            steps {
                echo 'Testing...'
            }
        }
        stage('Build') {
            steps {
                echo 'Building...'
            }
        }
        stage('Deploy on test') {
            steps {
                echo 'Deploying on test...'
            }
        }
        stage('Deploy on prod') {
            steps {
                echo 'Deploying on prod...'
                echo "this is to trigger the webhook"
                echo "this is to trigger the webhook 2"
                echo "this is to trigger the webhook 2"
            }
        }
        stage('Run Command') {
            steps {
                bat 'echo %DATE%'   // prints date in CMD
                bat 'dir'           // lists files
            }
        }
        stage('Print Variables') {
            // u can also check whether the system is linux or not, do chat gpt for that
            steps {
                bat 'echo Hello, my name is %MY_NAME%, project is %PROJECT%, and Build Number is %BUILD_NUMBER%'  // BUILD_NUMBER is inbuilt env variable 
            }
            //this is to configure webhook

        }
        stage('Print Parameters') {
            steps {
                bat 'echo Hello, my name is %MY_NAME1%, project is %PROJECT1%, environment is %ENVIRONMENT%, and Build Number is %BUILD_NUMBER%'
            }
        }
    }
  post {
        always {
            echo "This always runs (success or failure)."
        }
        success {
            echo "Pipeline succeeded ✅"
        }
        failure {
            echo "Pipeline failed ❌"
        }
        unstable {
            echo "Pipeline unstable ⚠️"
        }
        aborted {
            echo "Pipeline aborted ⏹"
        }
    }


}

