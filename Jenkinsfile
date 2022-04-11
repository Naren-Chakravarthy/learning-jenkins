pipeline {
  agent any
    options {
    ansiColor('xterm')
    }
    environment {
    ENV_URL = "pipeline.google.com"
    SSH_CRED = credentials("SSH")
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
         sh "echo '\033[34mHello\033[0m \033[33mcolorful\033[0m \033[35mworld!\033[0m'"
       }
     }
  }
}