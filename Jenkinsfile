pipeline {
  agent any

  tools {
    jdk 'java8'
    maven 'maven'
  }
  
  
stages {
    stage('Git checkout'){
      steps {
        git branch: 'feature',
        url: 'https://github.com/manojdesen1/multi.git'
      }
    }
  stage('maven bulid'){
    steps{
      sh 'mvn clean install'
    }
  }   
 stage ('Sonarqube Analysis'){
           steps {
           withSonarQubeEnv('sonarqube') {
           sh '''
           mvn -e -B sonar:sonar -Dsonar.java.source=1.8 -Dsonar.host.url="${sonar_url}" -Dsonar.login="${sonar_username}" -Dsonar.password="${sonar_password}" -Dsonar.sourceEncoding=UTF-8
           '''
           }
         }
      } 
 }
}
