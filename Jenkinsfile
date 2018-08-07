pipeline {
  agent {
    node {
      label 'pool_build'
    } 
  }
  stages {
    stage('Initialize') {
      steps {
        sh 'export BITGOJS_TEST_PASSWORD=${BITGOJS_TEST_PASSWORD}'
      }
    }
    stage('Build') {
      steps {
        sh 'npm install'
      }
    }
    stage('Unit Test') {
      steps {
        sh 'npm run test'
      }
    }
    stage('Test Integration') {
      steps {
        sh 'npm run test-integration'
      }
    }
    stage('Code Coverage') {
      steps {
        sh 'npm run coverage'
      }
    }
    stage('Lint') {
      steps {
        sh 'npm run lint'
      }
    }
    stage('Test Report') {
      steps {
        echo 'Set up reports here'
      }
    }
  }
}