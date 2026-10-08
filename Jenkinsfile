pipeline {
    agent any
    tools {
        maven 'Maven3'
    }
    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/abijithpa/maven-package-demo.git'
            }
        }
        stage('Package') {
            steps {
                sh 'mvn clean package'
            }
        }
        stage('Run JAR') {
            steps {
                // Note: We use sh and a single forward slash / for macOS paths
                sh 'java -cp target/maven-package-demo-1.0.jar com.example.App'
            }
        }
    }
}
