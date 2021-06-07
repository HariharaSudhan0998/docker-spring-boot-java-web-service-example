pipeline {
   agent any

  stages {
     stage('Compile') {
     steps {
        sh(script: 'mvn compile')
        echo 'Compile...'
     }
   }
  }
}
