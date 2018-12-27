#!groovy
properties([buildDiscarder(logRotator(artifactDaysToKeepStr: '', artifactNumToKeepStr: '', daysToKeepStr: '', numToKeepStr: '3'))])

node {
   /* 
    stage('Checkout') { 
   git branch: 'development', credentialsId: '84e76cf1-0abb-47af-bcfe-a33d7d9ce5aa', url: 'https://github.com/devopspeddireddy/maven-web-application.git'
   }
 */
 
 stage('Checkout'){

     checkout scm
  }
  
   stage('Testing')
   {
    if(isUnix()){
     sh 'mvn test'
      }
      else{
       bat 'mvn test'   
      }
   }
   /*
   stage('SonarQube Report Generation')
   {
    if(isUnix()){
     sh 'mvn sonar:sonar'
      }
      else{
       bat 'mvn sonar:sonar'   
      }
   }
    
    stage('NexusDeploy')
   {
    if(isUnix()){
     sh 'mvn deploy'
      }
      else{
       bat 'mvn deploy'   
      }
   }
   
   stage ('Deploy to Tomcat'){
       
       sh 'echo deploying application into tomcat'
       sh 'cp $WORKSPACE/target/*.war C:\DevopsSoftwares\Tomcat\apache-tomcat-9.0.13\webapps\'
       sh 'echo deploymnet done'
   }
   */
   stage ('Email Notifcation'){
       
       mail bcc: '', body: '''Build done

Regards,
Mithun Technologies''', cc: 'pedda.uk@gmail.com', from: '', replyTo: '', subject: 'Deployment done', to: 'pedda.uk@gmail.com'
   } 
    
}
