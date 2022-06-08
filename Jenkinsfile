node(){
  stage("git checkout"){
  checkout([$class: 'GitSCM', branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/muraliphani/project-dento.git']]])
  
  }
  stage("maven build"){
  sh"mvn clean install"
  }

}
