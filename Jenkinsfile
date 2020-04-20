pipeline {
     agent any
     stages {
        stage('Upload to AWS') {
            steps {
                withAWS(region:'us-west-2', credentials:'aws-static') {
                    sh 'echo "Currently uploading index.html file to S3..."'
                    s3Upload(pathStyleAccessEnabled: true, payloadSigningEnabled: true, file:'index.html', bucket:'mike-ajala-01')
                }
            }
        }
     }
}
