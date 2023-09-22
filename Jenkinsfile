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

        stage('Create Log File') {
          environment {
            name = 'diya'
          }
          steps {
            writeFile(file: 'LogFile.log', text: "The env is ${envt} and name is ${name}", encoding: 'UTF-8')
          }
        }

      }
    }

    stage('Deploy') {
      when {
        branch 'main'
      }
      parallel {
        stage('Deploy') {
          steps {
            input(message: 'Do you want to proceed?', id: 'Yes')
            echo 'Deploying code'
          }
        }

        stage('Archive Artifacts') {
          steps {
            archiveArtifacts 'LogFile.log'
          }
        }

      }
    }

  }
  environment {
    envt = 'INT'
  }
}