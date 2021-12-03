pipeline {
    agent any
   //agent {docker {image 'maven:3.6.3'}}
   environment{
       dockerHome=tool "myDocker"
       mavenHome=tool "myMaven"
       PATH="$dockerhome/bin:$mavenHome/bin:$PATH"
   }
    stages {
        stage('Build') {
            steps {
                sh 'mvn --version'
                sh 'docker --version'
                echo 'Path : $PATH'
            }
        }
        stage('Test') {
            steps {
                echo 'Test'
            }
        }
        stage('Integration Test') {
            steps {
                echo 'Integration Test'
            }
        }
    }

    post{

        always{
            echo 'always'
        }

        success{
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
