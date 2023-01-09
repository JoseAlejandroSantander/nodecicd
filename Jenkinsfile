pipeline {
    agent any
    stages {
        stage('docker build') {
            steps {
                echo "init"
                script {
                    sh "echo 'hola'"
                    sh "docker ps"
                }
                script {
                    sh "docker build -t ${name-app} ."
                }
                script {
                    sh "docker tag ${name-app} JoseAlejandroSantander/nodecicd:${BUILD_NUMBER}"
                }
            }
        }
        stage('docker push') {
            steps {
                script {
                    sh "echo $dockerhub_PSW | docker login -u $dockerhub_USR --password-stdin"
                }
                script {
                    sh "docker push JoseAlejandroSantander/nodecicd:${BUILD_NUMBER}"
                }
            }
        }
    }
}