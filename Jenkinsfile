node('master') 
{
   stage('continuous download') 
   {
    git 'https://github.com/vijay-1474/MyDevops.git'
   }
   stage('continuous build') 
   {
   sh 'mvn package'
   }
   stage('QA_Deployment') 
   {
   sh 'scp /home/ubuntu/.jenkins/workspace/Pipeline_Script/webapp/target/webapp.war ubuntu@172.31.37.225:/var/lib/tomcat9/webapps/QA.war'
   }
   stage('Delivery') 
   {
       input message: 'waiting for DM approval', submitter: 'harish'
    sh 'scp /home/ubuntu/.jenkins/workspace/Pipeline_Script/webapp/target/webapp.war ubuntu@172.31.31.209:/var/lib/tomcat9/webapps/PROD.war'
   }
}
