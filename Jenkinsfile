pipeline {
  agent any
  tools {
    maven 'Maven' 
  }
  stages {
    stage ('Build') {
      steps {
        bat 'mvn clean install'
      }
    }
    stage ('Deploy') {
      steps {
        script {
          deploy adapters: [tomcat8(credentialsId: 'tomcat_user', path: '', url: 'http://ec2-http:// ec2-100-26-35-113:8080/.compute-1.amazonaws.com:8080')], contextPath: '', onFailure: false, war: '**/*.war' 
        }
      }
    }
  }
}
