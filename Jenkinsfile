pipeline {
  agent any
  stages {
    stage('Second Stage') {
      steps {
        echo '"First Step ${params.DBServerName}"'
      }
    }
  }
  environment {
    DBServerName = 'hello'
  }
  parameters {
    string(name: 'BuildNum', defaultValue: 'BuildNum', description: 'Build Number Eg Release-153')
    booleanParam(name: 'CanRestartServer', defaultValue: 'false', description: 'Restart Required')
    string(name: 'DBServerName', defaultValue: 'DBServerName', description: 'Database Server Name Eg desktop-icvg5t9')
    string(name: 'DBUserName', defaultValue: 'DBUserName', description: 'Database User Name Eg demouser')
    string(name: 'DBUserPwd', defaultValue: 'DBUserPwd', description: 'Database User Password Eg demopwd')
    string(name: 'ImplScriptsLoc', defaultValue: 'ImplScriptsLoc', description: 'Implementation Scritps Location Eg FolderCUsersSowmyaDesktopHareen')
    string(name: 'ImplScripts', defaultValue: 'ImplScripts', description: 'Implementation Scripts Eg sqlfile1.sql')
    string(name: 'RBScriptsLoc', defaultValue: 'RBScriptsLoc', description: 'Rollback Scripts Location Eg CUsersSowmyaDesktopHareen')
    string(name: 'RBScripts', defaultValue: 'RBScripts', description: 'Rollback Scripts Eg sqlfile1.sql')
  }
}