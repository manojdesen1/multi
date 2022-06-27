pipeline {
  agent any

  tools {
    jdk 'java'
    maven 'maven'
  }
  
  
stages {
    stage('Git checkout'){
      steps {
        git branch: '{feature}',
        url: 'https://github.com/manojdesen1/multi.git'
      }
    }
    
 
 }
}
