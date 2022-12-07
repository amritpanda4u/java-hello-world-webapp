pipeline{
    agent {label "java-build-node"}
    
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
    }
}
