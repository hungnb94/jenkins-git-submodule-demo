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
        docker {
          image 'hungnb94/androidsdkmacos'
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
        docker {
          image 'hungnb94/androidsdkmacos'
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
