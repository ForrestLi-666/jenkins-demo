pipeline {
  agent any
  stages {
    stage('Build') {
      parallel {
        stage('Build') {
          steps {
            echo 'Building..'
          }
        }

        stage('CheckCode') {
          steps {
            bat(encoding: 'UTF-8', script: 'cd /d D:\\AllWorkSpace\\MavenCICD\\demo mvn install')
          }
        }

      }
    }

    stage('Test') {
      steps {
        echo 'Testing..'
      }
    }

    stage('Deploy') {
      steps {
        echo 'Deploying....'
      }
    }

  }
}