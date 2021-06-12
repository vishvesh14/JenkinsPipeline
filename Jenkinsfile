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

        stage('Report') {
          steps {
            writeFile(file: 'LogTestFile.txt', text: 'This is a automation test log file')
          }
        }

      }
    }

    stage('Deploy') {
      steps {
        echo 'Deploying the application'
        input(message: 'Do you want to Deploy', id: 'Ok')
      }
    }

  }
  environment {
    ChromeDriverPath = 'C:\\Program Files (x86)\\Google\\Chrome\\Application'
  }
}