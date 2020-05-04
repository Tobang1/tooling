pipeline {
    agent {
        docker {
            image 'docker:latest'
            // args '-v /root/.m2:/root/.m2'
        }
    }
  stages {
    stage('Clean Workspace'){
      steps {
          script {
          // Clean Up
          sh 'echo "cleaning Up workspace"'
        }
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