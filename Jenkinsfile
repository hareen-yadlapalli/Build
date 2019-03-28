pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        echo 'Starting the buil'
      }
    }
    stage('Run SQL in SMK') {
      steps {
        echo 'Executing SQL in SMK'
      }
    }
    stage('Deploy to SMK') {
      steps {
        echo 'Deploying to SMK'
      }
    }
    stage('Restart SMK Apps') {
      steps {
        echo 'Restarting SMK Apps'
      }
    }
  }
}