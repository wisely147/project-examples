pipeline {
  agent {
    docker {
      image 'tomcat'
      args '-p 8082:8080'
    }

  }
  stages {
    stage('Building') {
      steps {
        sh 'mvn -f maven-example/pom.xml compile'
      }
    }
    stage('Testing') {
      steps {
        sh 'mvn -f maven-example/pom.xml test'
      }
    }
    stage('Packing') {
      steps {
        sh 'mvn -f maven-example/pom.xml install'
      }
    }
    stage('Publishing') {
      steps {
        sh 'mvn -f maven-example/pom.xml deploy'
      }
    }
  }
}