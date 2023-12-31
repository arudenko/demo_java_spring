pipeline {
    agent {
        label 'ssh-agent'
    }
    stages {
        stage('Build Java') {
            steps {
                script {
                    sh './mvnw install'
                }
            }
        }

        stage ('Build Docker Image') {
            steps {
                script {
                    sh 'whoami'
                    sh 'docker build --build-arg JAR_FILE=target/demo_java_spring-0.0.1-SNAPSHOT.jar -t com.example.demo_java_spring/demo_java_application .'
                }
            }
        }
    }
}
