node{
 
 properties([
    buildDiscarder(logRotator(numToKeepStr: '3')),
    pipelineTriggers([
        pollSCM('* * * * *')
    ])
])

 def mavenHome = tool name: 'maven3.6.1', type: 'maven'
 
 stage('CheckoutCode') {
 git branch: 'master', credentialsId: '9ca9e08b-fc06-4630-ba0e-253718721658', url: 'https:https://github.com/flipkart1234/maven-web-application.git'
 }  
  
  stage('Build') {
    sh "${mavenHome}/bin/mvn clean package"
  }
}
