pipeline {
  agent {
    kubernetes {
      yaml """
apiVersion: v1
kind: Pod
spec:
  containers:
  - name: alpine
    image: alpine
    tty: true
"""
    }
  }
  triggers {
    eventTrigger jmespathQuery("eventName=='triggerLoad'")
  }
  stages {
    stage('Load 01') {
      steps {
        mockLoad 60
      }
    }
    stage('Load 02') {
      steps {
        mockLoad 60
      }
    }
    stage('Load 03') {
      steps {
        mockLoad 60
      }
    }
    stage('Load 04') {
      steps {
        mockLoad 60
      }
    }
  }
}
