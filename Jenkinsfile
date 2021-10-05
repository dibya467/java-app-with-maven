pipeline {
  agent any
  stages {
    stage('Log Tool Version') {
      parallel {
        stage('Log Tool Version') {
          steps {
            bat 'mvn --version git --version java -version'
          }
        }

        stage('Check for POM') {
          steps {
            fileExists 'pom.xml'
          }
        }

      }
    }

    stage('Build with Maven') {
      steps {
        bat 'mvn test compile'
      }
    }

    stage('Post Build Step') {
      steps {
        writeFile(file: 'status', text: 'Hey status')
      }
    }

  }
}