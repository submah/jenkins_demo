pipeline{
  agent { label 'maven_demo'}
    stages{
    stage('Cloning Repository'){
        git changelog: false, poll: false, url: 'https://github.com/submah/maven-jenkins-job.git'
    }
    stage('Maven Package Build'){
        sh 'mvn clean package'
    }
    stage('Deploying Package'){
        deploy adapters: [tomcat8(credentialsId: '3516710f-9b6f-4da9-8bfd-b9e9a65f06dd', path: '', url: 'http://34.66.61.7:8090')], contextPath: '/demojob', war: '**/*.war'
    }
    }
}


