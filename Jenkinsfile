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
        }
        stage("Jacoco") {
            step([$class: 'JacocoPublisher',
                  execPattern: 'target/*.exec',
                  classPattern: 'target/classes',
                  sourcePattern: 'src/main/java',
                  exclusionPattern: 'src/test*'
            ])
        }
    }
}