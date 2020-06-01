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
      parallel {
        stage('Deploy') {
          steps {
            echo 'Deploying....'
          }
        }

        stage('Copy') {
          steps {
            s3Upload(file:'C:\windows\system32\config\systemprofile\.m2\repository\demo\demo\0.0.1-SNAPSHOT\demo-0.0.1-SNAPSHOT.war', bucket: 'jekins-demo', path: 'demo-0.0.1-SNAPSHOT.war')
          }
        }

      }
    }

  }
}
