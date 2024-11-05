pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                //GET SOME CODE FROM A GITHUB REPO
                git branch: 'main', url: 'https://github.com/princesserh/lbg-vat-calculator.git'
            }
        }
        stage('SonarQube Analysis') {
            environment {
                scannerHome = tool 'sonarqube'
            }
            steps {
                withSonarQubeEnv('sonar-qube-1') {
                    sh "${scannerHome}/bin/sonar-scanner"
                }
            }
        }
    }
}