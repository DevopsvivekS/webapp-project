node{
  stage('SCM Checkout'){
    git 'https://github.com/DevopsvivekS/webapp-project.git'
  }
  stage('Compile-Package'){
    //Get Maven HomePATH
    def mvnHome =  tool name: 'maven-3.9.1', type: 'maven'
      sh "${mvnHome}bin/mvn package"
        }
     stage('Email-Notification'){
       mail bcc: '', body: '''Hi Welcome to jenkins email alerts
       Thanks
       Vivek''', cc: '', from: '', replyTo: '', subject: 'jenkins job', to: 'vivekextreme@gmail.com'
     }
  stage('Slack Notification'){
    slackSend baseUrl: 'https://hooks.slack.com/services/',
      channel: '#devopsprojects', 
      color: 'good', 
      message: 'welcome to jenkins slack!', 
      tokenCredentialId: 'slack-demo', 
      username: 'devopsprojects'
  }
}
