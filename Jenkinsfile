node {

stage('SCM'){
 git 'https://github.com/thomas-martin-adaming/testApp/tree/master/clientui'
 git 'https://github.com/thomas-martin-adaming/testApp/tree/master/config-server'
 git 'https://github.com/thomas-martin-adaming/testApp/tree/master/eureka-server'
 git 'https://github.com/thomas-martin-adaming/testApp/tree/master/microservice-compte-comptable'
 git 'https://github.com/thomas-martin-adaming/testApp/tree/master/microservice-journal'
 git 'https://github.com/thomas-martin-adaming/testApp/tree/master/microservice-utilisateur'
 git 'https://github.com/thomas-martin-adaming/testApp/tree/master/zuul-server'
}

stage('Compile'){
def mvnHome = tool name: 'maven-3' , type: 'maven'
sh "${mvnHome}/bin/mvn package"
}

stage('SonarQube') {
  def mvnHome = tool name: 'maven-3' , type: 'maven'
  sh "${mvnHome}/bin/mvn sonar:sonar -Dsonar.host.url=http://192.168.1.31:9000"
    }
}