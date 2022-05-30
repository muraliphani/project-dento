node(){
stage("Git checkout"){

checkout([$class: 'GitSCM', branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/muraliphani/project-dento.git']]])
sh "ls -l"

}
  
  stage("Maven Build"){
  sh "mvn install"
  }  

}
