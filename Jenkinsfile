pipeline {
    agent any
     tools {nodejs "NodeJs"}
    stages {
        stage('CheckOut from GitHub') {
            steps {
               git 'https://github.com/BABYDAMINENI/juice-shop.git'
            }
        }
        stage('Building the Application') {
            steps {
                echo 'install npm module'
                sh 'npm install'
            }      
        }
        stage('SonarQube Report'){   
            steps{
                withSonarQubeEnv('SonarQube'){
                    sh "npm install sonar-scanner"
                }
            }
            }
        stage('Deploy'){
            steps{
                  sh "npm start"
            }   
        }
    }
}
