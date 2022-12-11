pipeline{
    agent any
    
    tools {
        maven 'Maven-3.8'
    }
    stages{
        stage('checkout'){
           steps{
                checkout([$class: 'GitSCM', branches: [[name: '*/master']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/amritpanda4u/java-hello-world-webapp.git']]])
               }
        }
        stage('build'){
            steps{
               sh 'mvn clean install'
            }
        }
        stage('deploy to TC'){
            steps{
              deploy adapters: [tomcat9(credentialsId: 'TomcatServer', path: '', url: 'http://20.12.217.39:8080')], contextPath: null, war: '**/*.war'
            }
        }
    }
}
