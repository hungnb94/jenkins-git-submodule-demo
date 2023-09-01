pipeline {

  agent any

  options {
    timestamps()
  }
  environment {
    APP_ID = "com.baby518.camera2"
  }

  stages {
    stage('Build debug app') {
      agent {
        dockerfile {
          dir 'cicd/androidsdk'
          reuseNode true
          args "-v $HOME/.gradle:/root/.gradle"
        }
      }
      steps {
          sh "./gradlew assembleDebug"
      }
    }

    stage('Local unit test') {
      agent {
        dockerfile {
          dir 'cicd/androidsdk'
          reuseNode true
          args "-v $HOME/.gradle:/root/.gradle"
        }
      }
      steps {
          sh './gradlew test'
      }
    }
  }
}
