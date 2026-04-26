pipeline {
    agent any

    tools {
        jdk 'jdk21'   // must match your Jenkins tool name
    }

    stages {

        stage('Checkout') {
            steps {
                git branch: 'master', url: 'https://github.com/omkarmaha1620-collab/gradle1'
            }
        }

        stage('Build') {
            steps {
                sh 'chmod +x gradlew'
                sh './gradlew build'
            }
        }

        stage('Test') {
            steps {
                sh './gradlew test'
            }
        }

        stage('Run Application') {
            steps {
                sh './gradlew run'
            }
        }
    }

    post {
        success {
            echo 'Build SUCCESSFUL ✅'
        }
        failure {
            echo 'Build FAILED ❌'
        }
    }
}
