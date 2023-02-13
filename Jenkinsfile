pipeline {
  agent any
  tools {
    maven 'Maven'
  }

  stages {
    stage ('Build') {
      steps {
        sh 'mvn clean package'
      }
    }
    stage (Deploy to Tomcat) {
      steps {
        deploy adapters: [tomcat9(credentialsId: 'deploy2tomcat', path: '', url: 'http://18.188.204.164:8080/')], contextPath: '/web', war: '**/*.war'
      }
    }
  }
}
