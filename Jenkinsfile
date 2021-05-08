pipeline {
  agent any
  stages {
    stage('Test mvn') {
      steps {
         sh 'mvn test'
         sh 'mvn package'
      }
    }  
    
    stage('compilation') {
      steps {
         sh 'mvn package'
      }
    } 
    
    stage ('Publication du binaire') { 
      steps { 
        sh "curl -u admin:123456789 --upload-file  target/productcatalogue-0.0.1-SNAPSHOT.jar 'http://10.10.20.30:8081/repository/shopfront/app${BUILD_NUMBER}.jar' " 
 } 
 } 
  }
}
