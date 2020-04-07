pipeline {
   agent any

    environment {
        NUGET_KEY = 'abc'
    }

   stages {
      stage('Hello') {
         steps {
            echo 'Hello World'
         }
      }
      stage('Test') {
         steps {
            echo "${env.NUGET_KEY}"
         }
      }
   }
}