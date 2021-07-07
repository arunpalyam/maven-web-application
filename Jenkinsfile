node
{
    
def mavenHome = tool name: "maven3.8.1"

properties([buildDiscarder(logRotator(artifactDaysToKeepStr: '', artifactNumToKeepStr: '3', daysToKeepStr: '', numToKeepStr: '3')), pipelineTriggers([pollSCM('* * * * *')])])

stage('checkoutcode')
{
git branch: 'development', credentialsId: '6b360cd2-b11e-49cf-90ed-18fe751885f6', url: 'https://github.com/arunpalyam/maven-web-application.git'
}
stage('Build')
{
sh "${mavenHome}/bin/mvn clean package"
}
/*
stage('Execute Sonarqube Report')
{
sh "${mavenHome}/bin/mvn sonar:sonar"
}

stage('UploadingTheArtifactsIntoNexusRepository')
{
sh "${mavenHome}/bin/mvn deploy"
}

stage('UploadingTheArtifactsIntoNexusRepository')
{
sshagent(['c19ecd8c-ed55-49b1-bdb5-ec049210814d']) {
   sh "scp -o StrictHostKeyChecking=no target/maven-web-application.war ec2-user@13.127.240.238:/opt/apache-tomcat-9.0.48/webapps"  
}
}

stage ('send email notification')
{
emailext body: '''Build over 


Regards
Arun''', subject: 'Build Over', to: 'palyamarun@gmail.com'
}
*/
}
