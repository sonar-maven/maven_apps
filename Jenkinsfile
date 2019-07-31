node {
   
   stage('Code Checkout') { 
     git credentialsId: 'githubID', url: 'https://github.com/itrainbatman/maven_apps.git' 
    }
   stage('Build') {
    withMaven(jdk: 'java', maven: 'maven') {
     sh 'mvn clean compile'
      }
    }
   stage('Unit Test run') {
    withMaven(jdk: 'java', maven: 'maven') {
     sh 'mvn test'
      } 
    }
   stage('Sonar CodeAnalysis') {
     withMaven(jdk: 'java', maven: 'maven') {
        sh 'mvn sonar:sonar 
  -Dsonar.projectKey=sonar_maven 
  -Dsonar.organization=sonar-maven 
  -Dsonar.host.url=https://sonarcloud.io 
  -Dsonar.login=436517da3d4405422018244f3aeaf42a11cefb28
      }  
    }
   stage('Package to Jfrog') {
    withMaven(jdk: 'JDK-1.8', maven: 'Maven-3.6.1') {
     sh 'mvn package'
      }
    }
   
   stage('Deploy to Dev') {
     
    }
   stage('Automation Testing') {
     
    }
   stage('Deploy to Test') {
     
    }
   stage('Smoke Testing') {
     
    }
   stage('Deploy to Prod') {
     
    }
   stage('Acceptance Testing') {
     
    }
}
