pipeline {
    agent any
    
    environment{
        name = 'manoj'
    }
    
    parameters{
        string(name: 'person', defaultValue: 'MKP', description: "Type your Name")
        booleanParam(name: 'IsMale', defaultValue: 'true', description: "")
        choice(name: 'City', choices: ['Mumbai','Delhi','Pune'], description: "")
    }

    stages {
        stage('Run Command') {
            steps {
                sh '''
                date
                pwd
                ls
                cal 2023
                '''
            }
        }
        stage('ENV Variable') {
            environment{
                username = 'admin'
            }
            steps {
                sh 'echo "${BUILD_ID}"'
                sh 'echo "${name}"'
                sh 'echo "${username}"'
            }
        }
        stage('Build') {
            steps {
                echo 'Hello Build'
                sh 'echo "${name}"'
                sh 'echo "${username}"'
            }
        }
        stage('parameter') {
            steps {
                sh 'echo "${person}"'
                sh 'echo "${IsMale}"'
                sh 'echo "${City}"'
            }
        }
        stage('Deploy') {
            input{
                message "Should We Continue?"
                ok "Yes We Should"
            }
            steps {
                echo 'Hello Deploy'
            }
        }
        
    }
    post {
        always {
            echo 'I will always say Hello again!'
        }
    }
}
