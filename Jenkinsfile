pipeline {
  agent {
    docker {
      image 'node:14'
    }
  }
  stages {
    stage('Clone repository') {
      steps {
        git branch: 'main',
          url: 'https://github.com/harshhardikar/PES2UG20CS133_Jenkins.git'
      }
    }
    stage('Install dependencies') {
      steps {
        sh 'npm run build'
      }
    }
    stage('Test application') {
      steps {
        sh 'npm test'
      }
    }
    stage('Push Docker image') {
      steps {
        sh 'docker build -t jenkins:PES2UG20CS133 .'
        sh 'docker push docker run -p 8080:8080 -p 50000:50000 -it jenkins:PES2UG20CS133'
      }
    }
  }
  post {
    failure {
      echo 'Pipeline failed'
    }
  }
}
    
