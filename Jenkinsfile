pipeline {
  agent any
  stages {
    stage('build') {
      parallel {
        stage('build') {
          agent any
          environment {
            EXIT_STATUS = '${sh(                 returnStatus: true,                 script: \'exit 1\'             )}'
          }
          steps {
            sh 'echo "step 1"'
            echo 'build'
          }
        }
        stage('build1') {
          steps {
            sh 'printenv'
          }
        }
      }
    }
    stage('test') {
      steps {
        sh 'echo "step 2"'
        echo 'test'
      }
    }
    stage('deploy') {
      steps {
        sh 'echo "step 3"'
        echo 'deploy'
      }
    }
  }
  environment {
    EXIT_STATUS = '${sh(                 returnStatus: true,                 script: \'exit 1\'             )}'
  }
}