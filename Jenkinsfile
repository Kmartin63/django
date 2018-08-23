pipeline {
    agent {
        docker {
            image 'maven:3-alpine'
            args '-v /root/.m2:/root/.m2'
        }
    }
    stages {
        stage('Build') {
            steps {
                sh 'mvn -B -DskipTests clean package'
            }
        }
        stage('Test') {
            steps {
                sh 'mvn test'
            }
            post {
                always {
                    junit 'target/surefire-reports/*.xml'
                }
            }
        }
        stage('Deliver') {
            steps {
                sh './jenkins/scripts/deliver.sh'
            }
        }
        stage('Analyse') {
         steps {
           sh 'mvn sonar:sonar -Dsonar.host.url=http://172.28.21.67:9000 -Dsonar.login=a90ddc2ed0298418c15c1f56789097d80aec88c8'
         }
       }
    }
}
