pipeline{
  agent {
    docker {
      image 'maven:3-alpine'
      args '-v /root/.m2:/root/.m2'
    }
  }
  stages {
     stage("build & SonarQube analysis") {
            agent any
            steps {
              withSonarQubeEnv('Sonar-maven') {
                sh 'java -version'
                sh 'mvn clean package sonar:sonar'
              }
            }
          }
  }
}
