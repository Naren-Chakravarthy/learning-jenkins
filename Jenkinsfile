pipeline {
  agent any

  stages {
     stage ("one") {
       steps {
         echo "one"
         sh '''echo Hello 1
         echo hello 2'''

       }
     }
     stage ("two") {
            steps {
              echo "two"
            }
          }
  }
}