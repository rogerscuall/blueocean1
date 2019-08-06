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
   stage('Upload to AWS') {
        steps {
          withAWS(region:'us-east-1',credentials:'default') {
            s3Upload(pathStyleAccessEnabled:true, payloadSigningEnabled: true, file:'index.html', bucket:'c3pipelines-12324534')
          }
    }
  }
}
