pipeline {
    agent any
    options {
        withAWS(region:'ap-northeast-2', credentials:'aws-static')
    }
    parameters {
        string(name: 'filename', defaultValue: 'index.html', description: 'file to uploade')
        string(name: 'bucketname', defaultValue: 'jenkinspipeline', description: 'bucketname')
    }
    stages {
        stage('Upload to AWS') {
            steps {
                sh 'echo "Start Uploading"'
                s3Upload(file:${params.filename}, bucket:${params.bucketname}, path:${params.filename})
                sh ''' 
                    echo "Index.html Uploaded"
                    ls -lah
                   '''
            }
        }
    }
}