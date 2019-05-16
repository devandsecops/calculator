pipeline {
    agent any
    stages {
        stage("Checkout") {
            steps {
                git url: "https://github.com/devandsecops/calculator.git"
            }
        }
        stage("Compile") {
            steps {
                sh "./gradlew compileJava"
            }
        }
        stage("Unit Tests") {
            steps {
                sh "./gradlew test"
            }
        }
    }
}
