node{
 def maven = tool name: 'maven', type: 'maven'
 
 stage('CheckoutCode') {
     git credentialsId: 'github', url: 'https://github.com/flipkart1234/maven-web-application.git'
 }
 stage('generate artifact using maven build tool'){
   sh "${maven}/bin/mvn install"
 }
 stage('upload artifact'){
     nexusPublisher nexusInstanceId: 'nexus', nexusRepositoryId: 'quatric-snapshot', packages: []
     sh "${maven}/bin/mvn deploy"
 }
}
