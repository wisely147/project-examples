pipeline {
  agent {
    docker {
      image 'maven:3.5.0-jdk-8'
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