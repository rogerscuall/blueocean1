pipeline {
    agent any
    stages {
      stage('Lint HTML') {
        steps {
          sh 'tidy -q -e *.html'
        }
      }
      stage('Upload to AWS') {
        steps {
          withAWS(region:'us-east-1',profile:'default') {
           s3Upload(file:'mysimple.html', bucket:'udacity-demo1234')
          }
        }
      }
    }
}

