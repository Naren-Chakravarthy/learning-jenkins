pipeline {
  agent any

  stages {
     stage ("one") {
       steps {
         echo "one"
         sh '''echo Hello 1
         echo Hello 2'''
         addShortText background: '', borderColor: '', color: '', link: '', text: 'one'

       }
     }
     stage ("two") {
            steps {
              echo "two"
            }
          }
  }
}