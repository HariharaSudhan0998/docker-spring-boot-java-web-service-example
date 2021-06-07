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
     stage('Deploy to dev') {
       steps {	
	     script {
             sshagent (credentials:['productionserver']) { 
	     sh 'ssh -o StrictHostKeyChecking=no ec2-user@172.31.7.15 "killall -9 java; rm -rf docker-java-app-example.jar; ls -ltr; ps -ef |grep java  ;"'		
	     sh 'ssh -o StrictHostKeyChecking=no ec2-user@172.31.7.15 "pwd; ls -ltr; java -jar docker-java-app-example.jar 2>> /dev/null >> /dev/null &"; sleep 10; ps -ef |grep java'
   }
  }
				    
        echo 'Deploy to dev...'
     }
   }  
  }
}
