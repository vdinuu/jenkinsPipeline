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
        echo 'Deploying code'
        input(message: 'Do you want to proceed?', id: 'Yes')
      }
    }

  }
  environment {
    envt = 'INT'
  }
}