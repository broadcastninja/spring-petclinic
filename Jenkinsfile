#!groovy
pipeline {
   agent {
  docker {
    image "app:latest"
    args "-u root"  
    alwaysPull false
    reuseNode true
  }
}
   stages {     
    stage('Maven Install') {
      agent {         
       docker {          
         image 'maven:3.5.0'         
     }       
  }       
  steps {
       sh 'mvn clean install'
       }
     }
   }
 }
