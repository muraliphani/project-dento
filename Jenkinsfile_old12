pipeline {
    agent any
    environment {
        awscreds = 'ecr:us-east-2:aws-creds'
        appRegistry = "671903481871.dkr.ecr.us-west-2.amazonaws.com/devetest1"
        devtestRegistry = "https://671903481871.dkr.ecr.us-west-2.amazonaws.com"
    }
  stages {
    stage('Fetch code'){
      steps {
        git branch: 'main', url: 'https://github.com/muraliphani/project-dento.git'
      }
    }


    stage('Build'){
      steps {
        sh 'mvn install'
      }
    }

   
    stage('Docker Build Image') {
       steps {
       
         script {
                dockerImage = docker.build( appRegistry + ":$BUILD_NUMBER")
             }

     }
    
    }

    stage('Upload App Image') {
          steps{
            script {
              docker.withRegistry( devtestRegistry, awscreds) {
                dockerImage.push("$BUILD_NUMBER")
                dockerImage.push('latest')
              }
            }
          }
     }

  }
}
