pipeline{
    agent {label 'sonar'}
    stages{
       stage('Git Checkout Stage'){
            steps{
                git branch: 'main', url: 'https://github.com/Shreyas4321-s/java-example.git'
            }
         }        
       stage('Build Stage'){
            steps{
                sh 'mvn clean install'
            }
         }
        stage('SonarQube Analysis Stage') {
            steps{
                withSonarQubeEnv('SonarQube-jenkins') { 
                    sh "mvn clean verify sonar:sonar"
                }
            }
        }
    }
}
