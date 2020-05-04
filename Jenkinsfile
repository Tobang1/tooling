pipeline {
  agent any
  stages {
    stage('Clean Workspace'){
      steps {
        cleanWs()
      }
    }
    
    stage('Checkout'){
      steps {
      checkout([$class: 'GitSCM', 
      doGenerateSubmoduleConfigurations: false, 
      extensions: [], 
      submoduleCfg: [], 
      userRemoteConfigs: [[url: 'https://github.com/propitix/tooling.git']]])

      }
        }
        
    stage('Build') {
      steps {
        script {
          // Build
          sh 'docker build -t  489122420391.dkr.ecr.eu-west-2.amazonaws.com/tooling:latest .'
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