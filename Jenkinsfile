pipeline {  
  agent any
    tools{
        maven "Maven-3.9.9"
    }
    stages {
        stage('Clone') {
            steps {
               git 'https://github.com/Chenikala9/master_loans.git'
            }
        }
        stage('Build') {
            steps {
               sh 'mvn clean package'
            }
        }
        stage('Docker Image') {
            steps {
               sh ' docker build -t govardhan_image01 .'
            }
        }
       stage('Docker run') {
            steps {
               sh 'docker run --name govardhan_con01 -d -p 9090:8080 govardhan_image01  '
            }
        }
    }
}
