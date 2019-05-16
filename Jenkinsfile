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
        stage("Code Coverage") {
            steps {
                sh "./gradlew jacocoTestReport"
                publishHTML (target: [
                    reportDir: 'build/reports/jacoco/test/html',
                    reportFiles: 'index.html',
                    reportName: "JaCoCo Report"
                ])                
                sh "./gradlew jacocoTestCoverageVerification"
            }
        }
    }
}
