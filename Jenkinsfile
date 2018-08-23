pipeline {
  agent any
  stages {
    stage('Analyse') {
      agent {
        docker {
          image 'dsop/sonarqube-scanner'
          args '--entrypoint=""'
            args '--privileged=true'
        }
      }
      steps {
        sh 'sonar-scanner -Dsonar.projectKey=monproj -Dsonar.sources=. -Dsonar.host.url=http://172.28.21.67:9000 -Dsonar.login=c9cc31a0b1d774b4252691b7322ec195cb3aa141'
      }
    }
  }
}
