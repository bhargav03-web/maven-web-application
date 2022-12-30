node
{
    def mavenHome = tool name: "maven3.8.6"
    
    stage('CheckoutCode')
    {
        git branch: 'development', credentialsId: 'fc3f55ee-fbb1-4c4c-b5e0-fd39a099ec28', url: 'https://github.com/bhargav03-web/maven-web-application.git'
    }
    
    stage('Build')
    {
        sh "${mavenHome}/bin/mvn clean package"
    }
    
    stage('ExecuteSonarQubeReport')
    {
        sh "${mavenHome}/bin/mvn sonar:sonar"
    }
    
    stage('UploadArtifactIntoNexus')
    {
        sh "${mavenHome}/bin/mvn deploy"
    }
    
    stage('DeployAppIntoTomcat')
    {
        sshagent(['559e22a9-a610-4f0d-b61b-b744c40a6e44']) 
        {
            sh "scp -o StrictHostKeyChecking=no target/maven-web-application.war ec2-user@107.23.12.96:/opt/apache-tomcat-9.0.68/webapps/"
        }
    }
            
}
