pipeline {
    agent any
    stages {
        stage('docker build') {
            steps {
                echo "init"
                script {
                    sh "docker build -t prueba-cicd ."
                }
                script {
                    sh "docker tag ${name-app} JoseAlejandroSantander/nodecicd:${BUILD_NUMBER}"
                }
            }
        }
        stage('docker push') {
            steps {
                script {
                    sh "docker push JoseAlejandroSantander/nodecicd:${BUILD_NUMBER}"
                }
            }
        }
    }
}