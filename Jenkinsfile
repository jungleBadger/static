pipeline {
    agent any
    stages {
        stage('LINT HTML') {
            sh 'tidy -q -e *.html'
        }
        stage('Upload to AWS') {
            steps {
                sh 'echo "Hello World"'
                sh '''
                    echo "Multiline shell steps works too"
                    ls -lah
                '''
                withAWS(region:'us-east-2', credentials: 'aws-static') {
                    s3Upload(file: 'index.html', bucket: 'jenkins-static-udacity', path: 'index.html')
                }
            }
        }
    }
}
