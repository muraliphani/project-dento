node(){
  stage(){
  checkout([$class: 'GitSCM', branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/muraliphani/project-dento.git']]])
  
  }
  stage(){
  sh"mvn clean install"
  }

}
