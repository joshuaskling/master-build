pipeline {
  agent any
  parameters(string(name: 'submodule', defaultValue: ''))
  stages {
    stage('createViewBootstrapper') {
      steps {
        echo "VALUE: ${params.submodule}"
        sh '''
          echo "Running createViewBootstrapper"
        '''
      }
    }
    stage('updateUPDTClearCase') {
      steps {
        sh '''
          echo "Running updateUPDTClearCase"
        '''
      }
    }
    stage('UPDTcleaner') {
      steps {
        sh '''
          echo "Running UPDTcleaner"
        '''
      }
    }
  }
}
