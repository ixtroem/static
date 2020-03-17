pipeline {
    agent any
    options {
        withAWS(region:'ap-northeast-2', credentials:'aws-static')
    }
    stages {
        stage('Lint HTML') {
            steps {
                sh 'echo "Run tidy"'
                tidy -q -e *.html
            }
        }
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