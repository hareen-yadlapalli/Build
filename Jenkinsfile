pipeline {
  agent any
  stages {
    stage('Execute Scripts') {
      steps {
        build(job: 'ExecuteScripts', parameters: [
                                            [$class: 'StringParameterValue', name: 'DBServerName', value: "${params.DBServerName}"], 
                                            [$class: 'StringParameterValue', name: 'DBUserName', value: "${params.DBUserName}"],
                                            [$class: 'StringParameterValue', name: 'DBUserPwd', value: "${params.DBUserPwd}"],
                                            [$class: 'StringParameterValue', name: 'ImplScriptsLoc', value: "${params.ImplScriptsLoc}"],
                                            [$class: 'StringParameterValue', name: 'ImplScripts', value: "${params.ImplScripts}"],
                                            [$class: 'StringParameterValue', name: 'RBScriptsLoc', value: "${params.RBScriptsLoc}"],
                                            [$class: 'StringParameterValue', name: 'RBScripts', value: "${params.RBScripts}"]
                                           ])
        }
      }
      stage('Stage') {
        steps {
          echo '"First Step ${params.DBServerName}"'
          build 'PegaUnitTests'
          build(job: 'PegaUnitTests', parameters: [
                                            [$class: 'StringParameterValue', name: 'RBScriptsLoc', value: "${params.RBScriptsLoc}"]
                                            ])
        }
      }
      stage('Interactive Input') {
        steps {
          script {
            def userInput = input(
              id: 'userInput', message: 'Enter path of test reports:?',
              parameters: [
                [$class: 'TextParameterDefinition', defaultValue: 'None', description: 'Path of config file', name: 'Config'],
                [$class: 'TextParameterDefinition', defaultValue: 'None', description: 'Test Info file', name: 'Test']
              ])
              echo ("IQA Sheet Path: "+userInput['Config'])
              echo ("Test Info file path: "+userInput['Test'])
            }

          }
        }
      }
      environment {
        DBServerName = 'hello'
      }
      parameters {
        string(name: 'BuildNum', defaultValue: 'BuildNum', description: 'Build Number Eg Release-153')
        booleanParam(name: 'CanRestartServer', defaultValue: 'false', description: 'Restart Required')
        string(name: 'DBServerName', defaultValue: 'desktop', description: 'Database Server Name Eg mydesktop')
        string(name: 'DBUserName', defaultValue: 'demouser', description: 'Database User Name Eg demouser')
        string(name: 'DBUserPwd', defaultValue: 'demopwd', description: 'Database User Password Eg demopwd')
        string(name: 'ImplScriptsLoc', defaultValue: 'ImplScriptsLoc', description: 'Implementation Scritps Location')
        string(name: 'ImplScripts', defaultValue: 'sqlfile1.sql', description: 'Implementation Scripts Eg sqlfile1.sql')
        string(name: 'RBScriptsLoc', defaultValue: 'RBScriptsLoc', description: 'Rollback Scripts Location')
        string(name: 'RBScripts', defaultValue: 'sqlfile1.sql', description: 'Rollback Scripts Eg sqlfile1.sql')
      }
    }
