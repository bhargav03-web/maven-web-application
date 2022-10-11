node
{
   def mavenHome = tool name: "maven3.6.2"
  stage('CheckoutCode')
   {
    git branch: 'development', credentialsId: 'fc3f55ee-fbb1-4c4c-b5e0-fd39a099ec28', url: 'https://github.com/bhargav03-web/maven-web-application.git'
   }
   
  stage('Build')
   {
   sh "${mavenHome}/bin/mvn clean package"
   }
   
 /* stage('ExecuteSonarQubeReport')
   {
   sh "${mavenHome}/bin/mvn sonar:sonar"
   }
  
  stage('UploadArtifactIntoNexus')
   {
   sh "${mavenHome}/bin/mvn deploy"
   }
   
  stage('DeployAppIntoTomcat')
  {
   sshagent(['86752ca4-ce7c-4a7d-8880-127580f47cc1']) 
   {
    sh "scp -o StrictHostKeyChecking=no target/maven-web-application.war ec2-user@3.95.158.252:/opt/apache-tomcat-9.0.68/webapps/"
   }
  }
  
  stage('SendEmailNotification')
  {
   mail bcc: '', body: 'Build Over.', cc: 'deepthijeshri@gmail.com', from: '', replyTo: '', subject: 'Build Over', to: 'bhargav.teja02@gmail.com'
  }
*/
}
