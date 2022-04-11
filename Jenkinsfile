pipeline {
  agent any
  environment {
  ENV_URL = "pipeline.google.com"
  }
  stages {
     stage ("one") {
       steps {
         sh '''echo Hello 1
               echo Hello 2
               echo Environment url = ${ENV_URL}
         '''
       }
     }
     stage ("two") {
            steps {
              sh 'echo Environment url = ${ENV_URL}'
            }
          }
  }
}