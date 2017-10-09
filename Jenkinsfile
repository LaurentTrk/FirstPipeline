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
            sh 'hostname'
            
          },
          "Integration Tests": {
            sh 'echo \'Hello from sh\''
            node(label: 'Slave1') {
              echo 'Hello from Slave1 !!'
              script {
                println env.BUILD_ID
                println env.NODE_NAME
              }
              
            }
            
            script {
              test
            }
            
            
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