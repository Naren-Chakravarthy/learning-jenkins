pipeline {
  agent any

  stages {
     stage ("One") {
        environment {
        ENV_URL = "pipeline.google.com"
         }
       steps {
         sh '''echo Hello 1
               echo Hello 2
               echo Environment url = ${ENV_URL}
         '''
       }
     }
     stage ("Two") {
        environment {
        ENV_URL = "pipeline.google.com"
          }
       steps {
              sh 'echo Environment url = ${ENV_URL}'
            }
          }
  }
}