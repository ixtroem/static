pipeline {
    agent any
    options {
        withAWS(region:'ap-northeast-2', credentials:'aws-static')
    }
    stages {
        stage('Upload to AWS') {
            steps {
                sh 'echo "Start Uploading"'
                sh '''
                    s3Upload(file:"index.html", bucket:"jenkinspipeline")
                    echo "Index.html Uploaded"
                    ls -lah
                   '''
            }
        }
    }
}