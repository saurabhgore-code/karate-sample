pipeline {
  agent any
 stages {
    stage('Building Image') {
         steps{
             sh 'docker build -t karate-docker /home/billion/karate-sample'
         }
         }
    
   stage('clone the maven project'){
     steps {
       git 'https://github.com/saurabhgore-code/karate-sample.git'
     }
   }
       stage('run image') {
         steps {  
           sh 'docker run -t karate-docker' 
               }
       }

  }
}
