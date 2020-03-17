pipeline {
    agent any
    options {
        withAWS(region:'ap-northeast-2', credentials:'aws-static')
    }
    stages {
        stage('Upload to AWS') {
            steps {
                sh 'echo "Start Uploading"'
                s3Upload(file:'index.html', bucket:'jenkinspipeline', path:'index.html')
                sh ''' 
                    echo "index.html Uploaded"
                    ls -lah
                   '''
            }
        }
    }
}