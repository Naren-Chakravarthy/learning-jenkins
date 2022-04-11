pipeline {
  agent any
  environment {
  ENV_URL = "pipeline.google.com"
  }
  stages {
     stage ("one") {
       steps {
         echo "one"
         sh '''echo Hello 1
               echo Hello 2
               Environment url = ${ENV_URL}
            '''
         addShortText background: '', borderColor: '', color: '', link: '', text: 'one'

       }
     }
     stage ("two") {
            steps {
              echo "two"
              sh 'Environment url = ${ENV_URL}'
            }
          }
  }
}