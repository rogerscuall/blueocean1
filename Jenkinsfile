pipeline {
  agent {
    label 'master'
  }
  stages {
    stage('build') {
      steps {
        echo 'Hello World!'
        sh 'echo Hello from the shell'
        sh 'hostname'
        sh 'uptime'
        sh 'cat README.md'
        sh 'tidy -q -e *.html'
      }
    }
  }
}
