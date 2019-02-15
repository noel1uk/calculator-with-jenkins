pipeline {
    agent any
    stages{
        stage("Compile") {
            steps {
                sh "./mvnw install"
            }
        }
        stage("Unit test") {
            steps {
                sh "./mvnw test"
            }
            post {
                success {
                    junit 'target/*'
                    jacoco(execPattern: 'target/jacoco.exec')
                }
            }
        }
    }
}