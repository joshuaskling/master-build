pipeline {
  agent any
  environment {
    TEST = 'test environment variable'
  }
  parameters{
    string(name: 'stringInput', defaultValue: 'Hello')
    booleanParam(name: 'runCreate', defaultValue: true)
    booleanParam(name: 'runUpdate', defaultValue: false)
    booleanParam(name: 'runCleaner', defaultValue: true)
  }
  stages {
    stage('getConfig') {
      steps {
        props = readJSON 'config.json'
        echo props.id
      }
    }
    stage('createViewBootstrapper') {
      when{
        expression {params.runCreate == true}
      }
      steps {
        echo "VALUE: ${params.stringInput}"
        echo "VALUE: ${params.runCreate}"
        echo "VALUE: ${params.runUpdate}"
        echo "VALUE: ${params.runCleaner}"
        echo "${TEST}"
        sh '''
          echo "Running createViewBootstrapper"
        '''
        createViewBootstrapper()
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
        updateUPDTClearCase()
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
        UPDTcleaner()
      }
    }
  }
  post { 
        always { 
            echo 'I will always say Hello again!'
            echo "${TEST}"
          sh '''
            ls -ltr
          '''
        }
    }
}
