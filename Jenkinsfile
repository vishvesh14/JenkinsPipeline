pipeline {
  agent any
  stages {
    stage('Build') {
      parallel {
        stage('Build') {
          steps {
            echo 'Building the application'
          }
        }

        stage('Test') {
          steps {
            echo 'Testing the application'
            echo "Get Chrome Driver Path ${ChromeDriverPath}"
          }
        }

      }
    }

    stage('Deploy') {
      steps {
        echo 'Deploying the application'
      }
    }

  }
  environment {
    ChromeDriverPath = 'C:\\Program Files (x86)\\Google\\Chrome\\Application'
  }
}