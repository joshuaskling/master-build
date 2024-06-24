pipeline {
  agent any
  parameters {
        string(name: 'runCreate', defaultValue: true, description: 'Run createViewBootstrapper'),
          string(name: 'runCreate1', defaultValue: true, description: 'Run createViewBootstrapper'),
          string(name: 'runCreate2', defaultValue: true, description: 'Run createViewBootstrapper')
    }
  stages {
    stage('createViewBootstrapper') {
      steps {
        echo "VALUE: ${params.runCreate}"
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
