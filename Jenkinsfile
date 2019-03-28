pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        build 'BuildAndSaveToJFrog'
      }
    }
    stage('Run SQL in SMK') {
      steps {
        echo 'Executing SQL in SMK'
      }
    }
    stage('Deploy to SMK') {
      steps {
        build '	DeployBuildToTomcat-Dev'
      }
    }
    stage('Restart SMK Apps') {
      steps {
        echo 'Restarting SMK Apps'
      }
    }
  }
}