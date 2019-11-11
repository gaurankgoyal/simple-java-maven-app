pipeline {
  agent {
    docker {
      image 'maven:3-alpin'
      args '-v /root/.m2:/root/.m2'
    }

  }
  stages {
    stage('Build') {
      steps {
        sh 'mvn -B -DskipTests clean package'
      }
    }

    stage('TEST') {
      steps {
        sh 'mvn test'
      }
    }

    stage('Deliver') {
      steps {
        sh 'sh \'./jenkins/scripts/deliver.sh'
      }
    }

  }
}