pipeline {
  agent any
  stages {
    stage('Build') {
      parallel {
        stage('Build') {
          steps {
            echo 'Building code'
          }
        }

        stage('Test') {
          steps {
            echo 'Testing code'
            echo "Executed in Environment ${env}"
          }
        }

      }
    }

    stage('Deploy') {
      steps {
        echo 'Deploying code'
      }
    }

  }
  environment {
    env = 'INT'
  }
}