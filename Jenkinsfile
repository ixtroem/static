pipeline {
    agent any
    options {
        withAWS(region:'ap-northeast-2', credentials:'aws-static')
    }
    stages {
        stage('Upload to AWS') {
            steps {
                def filename = 'index.html'
                def bucketname = 'jenkinspipeline'
                sh 'echo "Start Uploading"'
                sh 's3Upload(file: ${filename}, bucket:${bucketname})'
                sh ''' 
                    echo "Index.html Uploaded"
                    ls -lah
                   '''
            }
        }
    }
}