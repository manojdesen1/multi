pipeline {
  agent any

  tools {
    jdk 'java8'
    maven 'maven'
  }
  environment {

      sonar_url = 'http://172.31.18.70:9000'
      sonar_username = 'admin'
      sonar_password = 'admin'
      
 }
  
  
stages {
    stage('Git checkout'){
      steps {
        git branch: 'master',
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
