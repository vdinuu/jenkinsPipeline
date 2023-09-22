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
            echo "Executed in Environment ${envt}"
          }
        }

      }
    }

    stage('Deploy') {
      steps {
        input(message: 'Do you want to proceed?', id: 'Yes')
        echo 'Deploying code'
      }
    }

  }
  environment {
    envt = 'INT'
  }
}