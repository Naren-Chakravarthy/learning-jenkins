pipeline {
  agent any
    options {
      ansiColor('xterm')
    }
    environment {
      ENV_URL = "pipeline.google.com"
      SSH_CRED = credentials("SSH")
    }
    parameters {
      string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')
      text(name: 'BIOGRAPHY', defaultValue: '', description: 'Enter some information about the person')
      booleanParam(name: 'TOGGLE', defaultValue: true, description: 'Toggle this value')
      choice(name: 'CHOICE', choices: ['One', 'Two', 'Three'], description: 'Pick something')
      password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'Enter a password')
    }
    triggers {
      pollSCM('*/2 * * * *')
    }
    tools {
      maven 'maven-3.8.5'
    }
  stages {
    stage ("One") {
    when {
      environment name: 'CHOICE', value: 'One'
    }
      steps {
      sh "echo Environment url = ${ENV_URL}"
      }
    }
    stage ("Two") {
      environment {
        ENV_URL = "stage.google.com"
      }
//       input {
//                       message "Should we continue?"
//                       ok "Yes, we should."
//                       submitter "alice,bob"
//                       parameters {
//                           string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')
//                       }
//      }
     when {
       environment name: 'CHOICE', value: 'Two'
     }
      steps {
      sh 'echo Environment url = ${ENV_URL}'
      sh 'env'
      sh "echo '\033[34mHello\033[0m \033[33mcolorful\033[0m \033[35mworld!\033[0m'"
      echo "Hello ${params.PERSON}"

      echo "Biography: ${params.BIOGRAPHY}"

      echo "Toggle: ${params.TOGGLE}"

      echo "Choice: ${params.CHOICE}"

      echo "Password: ${params.PASSWORD}"
      sh 'mvn --version'
      echo "Hello, ${PERSON}, nice to meet you."
      }
    }
  }
}