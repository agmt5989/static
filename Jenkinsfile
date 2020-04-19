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
                  withAWS(region:'us-east-2', credentials:'aws-static') {
                  sh 'echo "Currently uploading index.html file to S3..."'
                      s3Upload(pathStyleAccessEnabled: true, payloadSigningEnabled: true, file:'index.html', bucket:'mike-ajala-jenkins')
                  }
              }
         }
     }
}
