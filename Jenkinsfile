pipeline {
  agent any

  tools {
    jdk 'java'
    maven 'maven'
  }
  
  
stages {
    stage('Git checkout'){
      steps {
        git branch: '{develop}',
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
