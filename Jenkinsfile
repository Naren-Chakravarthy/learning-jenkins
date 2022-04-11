pipeline {
  agent any
    environment {
      ENV_URL = "pipeline.google.com"
      SSH_CRED = Credentials("SSH")
    }
  stages {
     stage ("One") {
       steps {
         sh '''echo Hello 1
               echo Hello 2
               echo Environment url = ${ENV_URL}
         '''
       }
     }
     stage ("Two") {
        environment {
          ENV_URL = "stage.google.com"
        }
       steps {
         sh 'echo Environment url = ${ENV_URL}'
         sh 'env'
       }
     }
  }
}