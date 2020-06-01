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

        stage('Go to project') {
          steps {
            bat(encoding: 'UTF-8', script: 'cd /d D:\\AllWorkSpace\\MavenCICD\\demo')
          }
        }

        stage('Mvn build') {
          steps {
            bat(script: 'mvn-install.bat', encoding: 'UTF-8')
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