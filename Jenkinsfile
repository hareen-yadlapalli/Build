pipeline {
  agent any
  stages {
    stage('First Stage') {
      steps {
        echo "First Step ${params.DBServerName}"
      }
    }
  }
  environment {
    DBServerName = 'hello'
  }
  parameters {
    string(name: 'DBServerName', defaultValue: 'test', description: 'Enter DB Server Name')
  }
}