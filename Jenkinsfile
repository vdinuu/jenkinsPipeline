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
}