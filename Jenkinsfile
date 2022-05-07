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
          deploy adapters: [tomcat8(credentialsId: 'tomcat_user', path: '', url: 'http://ec2-http:// ec2-3-82-22-1:8080/.compute-1.amazonaws.com:8080')], contextPath: '', onFailure: false, war: '**/*.war' 
        }
      }
    }
  }
}
