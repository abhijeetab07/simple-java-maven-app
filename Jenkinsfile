pipeline {
    agent {
        docker {
            image 'maven:3.8.1-adoptopenjdk-11' 
            args '-v /root/.m2:/root/.m2' 
        }
    }
    stages {
          stage('SonarQube Analysis') {
              steps {
                    def scannerHome = tool 'SonarScanner';
                    withSonarQubeEnv() {
                    sh "${scannerHome}/bin/sonar-scanner"
          }
        }
      }
    }
}
