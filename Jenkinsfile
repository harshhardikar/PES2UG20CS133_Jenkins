pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        sh 'g++ -o PES2UG20CS170-1 abc.cpp'
        echo 'Building stage Successful'
      }
    }
    stage('Test') {
      steps {
        sh './PES2UG20CS170-1'
        echo 'Testing stage Successful'
      }
    }
    stage('Deploy') {
      steps {
        echo 'Deploying stage Successful'
      }
    }
}
  post {
    failure {
      echo 'Pipeline failed'
    }
  }
}
    
