pipeline {
  agent any
  parameters{
    string(name: 'stringInput', defaultValue: 'Hello')
    booleanParam(name: 'runCreate', defaultValue: true)
    booleanParam(name: 'runUpdate', defaultValue: false)
    booleanParam(name: 'runCleaner', defaultValue: true)
  }
  stages {
    stage('createViewBootstrapper') {
      when{
        expression {params.runCreate == true}
      }
      steps {
        echo "VALUE: ${params.stringInput}"
        echo "VALUE: ${params.runCreate}"
        echo "VALUE: ${params.runUpdate}"
        echo "VALUE: ${params.runCleaner}"
        sh '''
          echo "Running createViewBootstrapper"
        '''
      }
    }
    stage('updateUPDTClearCase') {
      when{
        expression {params.runUpdate == true}
      }
      steps {
        sh '''
          echo "Running updateUPDTClearCase"
        '''
      }
    }
    stage('UPDTcleaner') {
      when{
        expression {params.runCleaner == true}
      }
      steps {
        sh '''
          echo "Running UPDTcleaner"
        '''
      }
    }
  }
}
