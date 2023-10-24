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
  stages {
    stage('Load 01') {
      steps {
        mockLoad 60
      }
    }
  }
}
