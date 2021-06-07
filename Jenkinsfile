pipeline {
   agent any

  stages {
     stage('Compile') {
     steps {
        sh(script: 'mvn compile')
        echo 'Compile...'
     }
   }
   
     stage('package') {
     steps {
        sh(script: 'mvn package')
        echo 'Package...'
     }
   }
  }
}
