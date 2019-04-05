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
    string(name: 'DBServerName', defaultValue: 'DBServerName', description: 'desktop-icvg5t9')
    string(name: 'DBUserName', defaultValue: 'DBUserName', description: 'demouser')
    string(name: 'DBUserPwd', defaultValue: 'DBUserPwd', description: 'demopwd')
    string(name: 'ImplScriptsLoc', defaultValue: 'ImplScriptsLoc', description: 'FolderCUsersSowmyaDesktopHareen')
    string(name: 'ImplScripts', defaultValue: 'ImplScripts', description: 'sqlfile1.sql')
    string(name: 'RBScriptsLoc', defaultValue: 'RBScriptsLoc', description: 'CUsersSowmyaDesktopHareen')
    string(name: 'RBScripts', defaultValue: 'RBScripts', description: 'sqlfile1.sql')
  }
}
