node{
  stage('SCM Checkout'){
    git 'https://github.com/DevopsvivekS/webapp-project.git'
  }
  stage('Compile-Package'){
    // Get maven home path
    def mvnHome = tool name: 'Maven-3.9.1', type: 'maven'
    sh "${mvnHome}/bin/mvn package"  
  }
  stage('SonarQube Analysis'){
    def mvnHome = tool name: 'Maven-3.9.1', type: 'maven'
    withSonarQubeEnv('SonarQube'){
    sh "${mvnHome}/bin/mvn sonar:sonar"
     }
  }
  stage('Email-Notification'){
    mail bcc: '', body: '''Hi Welcome to jenkins email alerts
    Thanks
    vivek''', cc: '', from: '', replyTo: '', subject: 'jenkins job', to: 'vivekextreme@gmail.com'
  }
  stage('Slack notification'){
        slackSend baseUrl: 'https://hooks.slack.com/services/', 
        channel: '#jenkins-pipeline-demo',
        color: 'good',
        message: 'Welcome to Jenkins', 
        tokenCredentialId: 'slack-demo-1', 
        username: 'vivek singh'
  }
}
