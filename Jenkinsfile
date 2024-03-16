pipeline {
    agent any
    environment {
       name = 'priya'
    }
    parameters{
    string(name: 'your_name', defaultValue: 'asvani', description: "enter your name" )
    booleanParam(name: 'Is_latest', defaultValue: true, description: "is the code latest?")
    choice(name: 'env', choices: ['dev','test','prod'], description: "choose environment" )
    }

    stages {
        stage('Run-a-command') {
            steps {
                sh '''
                pwd
                whoami
                '''

            }
        }
        stage('Variables') {
         environment {
            username = 'harman'
         }
            steps {
               sh 'echo "${BUILD_ID}"'
               sh 'echo "${name}"'
               sh 'echo "${username}"'
            }
        }
        stage('parameters') {
            steps {
                sh 'echo "${your_name}"'
                sh 'echo "${username}"'
            }
        }
        stage('deploy-to-prod') {
        input {
        message "do you want to continue?"
        ok "yes please"
        }
            steps {
                echo 'deployment on prod'
               
            }
        }
    }
      post { 
        always { 
            echo 'I will always say Hello again!'
            }
        success { 
            echo 'congratulations....'
            }
        failure { 
            echo 'better luck next time'
            }
    } 

}
