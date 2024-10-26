node {
    stage('SCM') {
        checkout scm: [$class: 'GitSCM', branches: [[name: '*/main']], userRemoteConfigs: [[url: 'https://github.com/yourusername/casestudy44.git']]]
    }
    stage('SonarQube Analysis') {
        def mvn = tool 'Default Maven';
        withSonarQubeEnv() {
            sh "${mvn}/bin/mvn clean verify sonar:sonar -Dsonar.projectKey=casestudy44"
        }
    }
}
