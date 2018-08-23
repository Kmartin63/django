pipeline {
  agent any
  stages {
    stage('Analyse') {
      agent {
        docker {
          image 'dsop/sonarqube-scanner'
          args '--entrypoint=""'
        }
      }
      steps {
        sh 'sonar-scanner -Dsonar.projectKey=monproj -Dsonar.sources=. -Dsonar.login=c9cc31a0b1d774b4252691b7322ec195cb3aa141'
      }
    }
  }
}
