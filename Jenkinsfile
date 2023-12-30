pipeline {
    agent {
        label 'ssh-agent'
    }
    stages {
        stage('Build') {
            steps {
                script {
                    docker.image('maven:3-alpine').inside {
                        sh './mvnw clean install'
                    }
                    docker.build('com.example.demo_java_spring/demo_java_application', '--build-arg JAR_FILE=target/demo_java_spring-0.0.1-SNAPSHOT.jar .')
                }
            }
        }
    }
}
