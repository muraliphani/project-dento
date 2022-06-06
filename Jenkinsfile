node {
  stage('SCM') {
    checkout scm
  }
  stage('SonarQube Analysis') {
    //def mvn = tool 'Default Maven';
    withSonarQubeEnv() {
      sh "mvn clean verify sonar:sonar -Dsonar.projectKey=devtest1"
    }
  }
}
