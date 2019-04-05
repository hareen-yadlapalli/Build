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
    string(name: 'DBServerName', defaultValue: 'DBServerName', description: 'Database Server Name desktop-icvg5t9')
    string(name: 'DBUserName', defaultValue: 'DBUserName', description: 'Database User Name demouser')
    string(name: 'DBUserPwd', defaultValue: 'DBUserPwd', description: 'Database User Password demopwd')
    string(name: 'ImplScriptsLoc', defaultValue: 'ImplScriptsLoc', description: 'Implementation Scritps Location FolderCUsersSowmyaDesktopHareen')
    string(name: 'ImplScripts', defaultValue: 'ImplScripts', description: 'Implementation Scripts sqlfile1.sql')
    string(name: 'RBScriptsLoc', defaultValue: 'RBScriptsLoc', description: 'Rollback Scripts Location CUsersSowmyaDesktopHareen')
    string(name: 'RBScripts', defaultValue: 'RBScripts', description: 'Rollback Scripts sqlfile1.sql')
  }
}
