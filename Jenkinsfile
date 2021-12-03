pipeline {
    agent any
    environment {
        mavenHome = tool 'myMaven'
        PATH = "$mavenHome/bin:$PATH"
    }
    stages {
        stage('Checkout') {
            steps {
                sh 'mvn --version'
                echo 'Path : $PATH'
            }
        }
        stage('compile') {
            steps {
                sh 'mvn clean compile'
            }
        }
        
        stage('Test') {
            steps {
              sh 'mvn test'
            }
        }
        stage('Integration Test') {
            steps {
                sh 'mvn failsafe:integration-test failsafe:verify'
            }
        }
    }

    post {
        always {
            echo 'always'
        }

        success {
            echo 'success'
        }

        failure {
            echo 'fail'
        }

        changed {
            echo 'change'
        }
    }
}
