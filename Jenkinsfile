pipeline {
    agent any 
    tools {
        maven "Maven"
        jdk "jdk"
        git "git"
    }

    stages {
        stage('Checkout') {
            steps {
                // Get some code from a GitHub repository
                checkout([$class: 'GitSCM', branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/arpitsaxena599/maven-p.git']]])
            }
        }
        
        stage('Build') {
            steps {
                // Run Maven on a Unix agent.
                sh "mvn clean package"
            }
        }
         stage('Compile') {
             steps {
                   sh 'mvn clean compile'
                 }
            } 
        stage('Test') {
            steps {
                sh 'mvn test'
            }
        }
    }
}
