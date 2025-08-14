# Jenkins-deployment-using-pipeline-code
pipeline {
    agent any
    tools {
        maven "mymaven"
    }
    stages{
        stage('source-code') {
            steps {
                git 'https://github.com/koushikadari/one.git'
            }
        }
        stage('build and test'){
            steps{
                    sh 'mvn clean package'
                }
            }
        stage('artifact'){
             steps{
                nexusArtifactUploader artifacts: [[artifactId: 'myweb', classifier: '', file: 'target/myweb-8.7.1.war', type: 'war']], credentialsId: 'nexus', groupId: 'in.javahome', nexusUrl: '3.86.237.50:8081', nexusVersion: 'nexus3', protocol: 'http', repository: 'koushik', version: '8.7.1'
             }
           }
         stage('deploy'){
             steps{
                 deploy adapters: [tomcat9(alternativeDeploymentContext: '', credentialsId: 'tomcat', path: '', url: 'http://13.222.166.224:8080/')], contextPath: 'e-commerce', war: 'target/*.war'
             }
         }
       }
   }
