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
        sh 'sonar-scanner -Dsonar.projectKey=monproj -Dsonar.sources=. -Dsonar.host.url=http://172.28.21.67:9000 -Dsonar.login=37ab33c5f1a26a61d00e3690c410a77acfdeb04d'
      }
    }
  }
}
