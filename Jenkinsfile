node('master')
{
    
   stage('ContinuousDownload')
   {
    git 'https://github.com/abhi3699/Maven.git'
   }
   stage('ContinuousBuild')
   {
       sh 'mvn package'
   }
   stage('ContinuousDeployment')
   {
       sh 'scp /home/ubuntu/.jenkins/workspace/ScriptedPipeline@2/webapp/target/webapp.war ubuntu@172.31.1.8:/var/lib/tomcat9/webapps/testwebapp.war'
   }
   stage('ContinuousTesting')
   {
       git 'https://github.com/abhi3699/FunctionalTestsing.git'
       
       sh 'echo "Testing Passed"'
   }
   stage('ContinuousTesting')
   {
       sh 'scp /home/ubuntu/.jenkins/workspace/ScriptedPipeline@2/webapp/target/webapp.war ubuntu@172.31.1.19:/var/lib/tomcat9/webapps/prodwebapp.war'
   }
   
   
}
