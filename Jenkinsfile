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
                new File("demo.txt").write(env.BUILD_NUMBER)
              }
              
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