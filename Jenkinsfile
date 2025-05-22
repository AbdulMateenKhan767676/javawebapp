pipeline {
    agent any
    stages {
        stage("checkout"){
        steps{
            git 'https://github.com/AbdulMateenKhan767676/javawebapp.git'
            }
        }
        stage('test'){
        steps{
            sh 'mvn test'
            }
        }
        stage('artifact'){
        steps{
            sh 'mvn package'
            }
        }
        stage('artifact upload'){
        steps{
            nexusArtifactUploader artifacts: [[artifactId: 'SimpleWebApplication', classifier: '', file: '/home/jenkins/workspace/Simplewebapp/target/SimpleWebApplication-9.1.14.war', type: 'war']], credentialsId: 'Nexus', groupId: 'com.maven', nexusUrl: '15.206.211.8:8080', nexusVersion: 'nexus3', protocol: 'http', repository: 'project1', version: '9.1.14'
            }
        }
    }
}
