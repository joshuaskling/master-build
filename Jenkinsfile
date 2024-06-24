pipeline {
  agent any
  parameters([
    string(name: 'createViewBootstrapper', defaultValue: 'true'),
    string(name: 'updateUPDTClearCase', defaultValue: ''),
    string(name: 'UPDTcleaner', defaultValue: 'true')
  ])
  stages {
    stage('createViewBootstrapper') {
      steps {
        echo "VALUE: ${params.createViewBootstrapper}"
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
