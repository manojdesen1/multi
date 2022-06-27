pipeline {
  agent any

  tools {
    jdk 'Java'
    maven 'Maven'
  }
  
  
stages {
    stage('Git checkout'){
      steps {
        git branch: '{feature}',
        url: 'https://github.com/manojdesen1/multi.git'
      }
    }
    stage('Maven build'){
      steps {
        sh 'mvn clean install'
      }
    }
 
 }
}
