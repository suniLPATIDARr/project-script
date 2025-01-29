pipeline {
    agent any

    stages {
        stage('checkout') {
            steps {
                git 'https://github.com/suniLPATIDARr/project-script.git'
            }
        }
         stage('build') {
            steps {
                sh 'mvn clean'
                sh 'mvn package'
            }
        }
         stage('deploye') {
            steps {
                sh 'docker build -t testimage .'
                sh 'docker run -d --name newappcontainer1 -p 8082:8080 testimage'
            }
        }
    }
}
