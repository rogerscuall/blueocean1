pipeline {
    agent any
    stages {
      stage('Lint HTML') {
        steps {
          sh 'tidy -q -e *.html'
        }
      stage('Upload to AWS') {
        steps {
          withAWS(region:'us-east-1',credentials:'default') {
            s3Upload(pathStyleAccessEnabled:true, payloadSigningEnabled: true, file:'index.html', bucket:'c3pipelines-12312312312')
          }
        }
      }
    }
}
