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
                git branch: 'main', url: 'https://github.com/cabdiasismohamed/JenkinsDemo.git'
            }
        }

        stage('SonarQube Analysis') {
            steps {
                withSonarQubeEnv('MySonarQube') {
                   bat "C:\\sonar-scanner-5.0.1.3006-windows\\bin\\sonar-scanner -Dsonar.projectKey=MyProject -Dsonar.sources=src -Dsonar.host.url=http://localhost:9000 -Dsonar.login=sqa_0386504208aea515d3b9db5a3239c53b5e41030f"
                }
            }
        }
    }
}
