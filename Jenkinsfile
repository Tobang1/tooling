pipeline {
  agent any
  stages {
    stage('Clean Workspace'){
      steps {
        cleanWs()
      }
    }
    
    stage('Build') {
      steps {
        script {
          // Build
          sh 'docker build .'
        }
      }
    }


    stage('Test') {
      steps {
        script {
          // Build
          sh 'echo "Testing Stage"'
        }
      }
    }

    stage('Deploy') {
      steps {
        script {
          // Build
          sh 'docker push 489122420391.dkr.ecr.eu-west-2.amazonaws.com/tooling:latest'
        }
      }
    }
  }
}