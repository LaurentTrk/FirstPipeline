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
            node(label: 'Slave2') {
              echo 'Hello from Slave1 !!'
            }
            
            sleep 20
            
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