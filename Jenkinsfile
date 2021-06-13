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
          environment {
            LocalVariable = 'Hello this is Local variable'
          }
          steps {
            writeFile(file: 'LogTestFile.txt', text: "This is a automation test log file ${ChromeDriverPath} and ${LocalVariable}")
          }
        }

      }
    }

    stage('Deploy') {
        when{
            branch 'master'
        }
      parallel {
        stage('Deploy') {
          steps {
            echo 'Deploying the application'
            input(message: 'Do you want to Deploy ?', id: 'Ok')
          }
        }

        stage('Artificats') {
          steps {
            archiveArtifacts 'LogTestFile.txt'
          }
        }

      }
    }

  }
  environment {
    ChromeDriverPath = 'C:\\Program Files (x86)\\Google\\Chrome\\Application'
  }
}