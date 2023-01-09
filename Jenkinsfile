pipeline {
    agent any
    stages {
        stage('docker build') {
            steps {
                echo "init"
                sh "docker build -t prueba-cicd ."
                sh "docker tag prueba-cicd josesant/nodecicd:${BUILD_NUMBER}"
            }
        }
        stage('docker push') {
            steps {
                sh "docker push josesant/nodecicd:${BUILD_NUMBER}"
            }
        }
    }
}