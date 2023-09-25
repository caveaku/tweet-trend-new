pipeline {
    agent {
        node {
            label 'maven'
        }
    }

    stages {
        stage('Clone-Code') {
            steps {
                git branch: 'main', url: 'https://github.com/caveaku/tweet-trend-new.git'
            }
        }
      stage('SonarQube analysis') {
    environment {
      scannerHome = tool 'valaxy010-sonar-scanner'
    }
    steps{
    withSonarQubeEnv('valaxy-sonarqube-server') { // If you have configured more than one global server connection, you can specify its name
      sh "${scannerHome}/bin/sonar-scanner"
    }
    }
  }  
    }
}
