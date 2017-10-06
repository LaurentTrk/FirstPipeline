pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        echo 'This is a build'
      }
    }
    stage('Tests') {
      steps {
        parallel(
          "Tests": {
            echo 'Beginning tests'
            
          },
          "Integration Tests": {
            sh 'echo \'Hello from sh\''
            
          }
        )
      }
    }
    stage('Deploy') {
      steps {
        input 'Are you ok ?'
      }
    }
  }
}