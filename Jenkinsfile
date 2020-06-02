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

    stage('Move') {
      parallel {
        stage('Move') {
          steps {
            echo 'Copy..'
          }
        }

        stage('Copy') {
          steps {
            bat(script: 'copy.bat', encoding: 'UTF-8')
          }
        }

      }
    }

    stage('Deploy') {
      parallel {
        stage('Deploy') {
          steps {
            echo 'Deploying....'
          }
        }

        stage('Upload') {
          steps {
            s3Upload(file: 'demo-0.0.1-SNAPSHOT.war', bucket: 'jekins-demo', path: 'demo-0.0.1-SNAPSHOT.war')
          }
        }

      }
    }

  }
}