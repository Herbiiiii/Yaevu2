pipeline {
    agent {
        docker {
            image 'maven:3.8.1-jdk-11' // Используем образ с Maven и JDK
        }
    }
    stages {
        stage('Build') {
            steps {
                sh 'mvn clean package' // Сборка проекта с помощью Maven
            }
        }
    }
    post {
        success {
            archiveArtifacts artifacts: 'target/*.jar', fingerprint: true // Архивируем готовый .jar файл
        }
    }
}
