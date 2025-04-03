pipeline {
    agent any

    environment {
        SONAR_SCANNER_HOME = 'C:\\sonar-scanner-5.0.1.3006-windows\\bin'
        SONAR_HOST_URL = 'http://localhost:9000'
        SONAR_PROJECT_KEY = 'MyProject'
        SONAR_LOGIN = 'sqa_0386504208aea515d3b9db5a3239c53b5e41030f'
    }

    stages {
        stage('Checkout Code') {
            steps {
                git 'https://github.com/cabdiasismohamed/JenkinsDemo.git'
            }
        }

        stage('SonarQube Analysis') {
            steps {
                withSonarQubeEnv('MySonarQube') {
                    bat "${SONAR_SCANNER_HOME}\\sonar-scanner -Dsonar.projectKey=${SONAR_PROJECT_KEY} -Dsonar.sources=src -Dsonar.host.url=${SONAR_HOST_URL} -Dsonar.login=${SONAR_LOGIN}"
                }
            }
        }
    }
}
