pipeline {
  agent any
  environment {
    DOCKER_IMAGE = "my-app"
    DOCKER_REGISTRY = "147356820214.dkr.ecr.us-east-2.amazonaws.com/node-js"
  }
  stages {
    stage('Clone') {
      steps {
        git ' https://github.com/saritaaaaaaa/node-js-sample.git'
      }
    }
    stage('Test') {
      steps {
        sh 'npm install'
        sh 'npm test'
      }
    }
    stage('Build') {
      steps {
        script{
        def dockerfile = 'Dockerfile'
        def dockerImage = docker.build("$DOCKER_REGISTRY/$DOCKER_IMAGE", "-f $dockerfile .")
        }
       
      }
      }
    }
   }
