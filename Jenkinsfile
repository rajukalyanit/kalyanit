pipeline {
    agent any

    stages {
        stage('cleanup') {
            steps {
                deleteDir()
            }
        }
        stage('git'){
            steps {
                checkout scmGit(branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/rajukalyanit/kalyanit.git']])
            }
        }
        stage('maven'){
            steps {
               bat 'mvn clean package'
            }
        }
         stage('tomcat'){
            steps {
               bat 'mvn tomcat7:deploy'
            }
        }
        stage('send email'){
            steps {
               bat 'echo "sending emails'
            }
        }
        
    }
}
