pipeline {
  agent any
  stages {
    stage('Test') {
      steps {
        sh 'mvn test'
      }
    }

    stage('Build') {
      steps {
        sh 'mvn clean install'
      }
    }

    stage('Deploy ') {
      parallel {
        stage('Deploy ') {
          steps {
            echo 'war/jar deployed '
          }
        }

        stage('Pre-Prod/Staging') {
          steps {
            echo 'war deployed on staging server'
          }
        }

      }
    }

    stage('Deploy on Prod ') {
      steps {
        echo 'war deployed on Prod server'
      }
    }

  }
}