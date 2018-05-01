pipeline {
  agent none
  stages {
    stage('Event Trigger') {
      when {
        expression {
          return currentBuild.rawBuild.getCause(com.cloudbees.jenkins.plugins.pipeline.events.EventTriggerCause)
        }
        
      }
      steps {
        echo 'triggered by published event'
      }
    }
  }
  triggers {
    eventTrigger(simpleMatch('beeEvent'))
  }
}