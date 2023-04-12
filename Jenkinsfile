node{
  stage('SCM Checkout'){
    git 'https://github.com/DevopsvivekS/webapp-project.git'
  }
  stage('Compile-Package'){
    // Get maven home path
    def mvnHome = tool name: 'Maven-3.9.1', type: 'maven'
    sh "${mvnHome}/bin/mvn package"  
  }
}
