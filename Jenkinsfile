node{
  stage('SCM Checkout'){
    git 'https://github.com/DevopsvivekS/webapp-project.git'
  }
  stage('Compile-Package'){
    //Get Maven HomePATH
    def mvnHome =  tool name: 'maven-3.9.1', type: 'maven'
    sh "${mvnHome}/bin/mvn package"
        }
        
  }
