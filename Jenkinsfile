pipeline {
    agent any
    stages {
        stage('Upload to AWS') {
            steps {
                sh 'echo "Hello World"'
                sh '''
                    echo "Multiline shell steps works too"
                    ls -lah
                '''
                withAWS(region:'us-east-2', credentials: 'AKIAVLN56CPPUB6HNJE2') {
                    s3Upload(file: 'index.html', bucket: 'jenkins-static-udacity', path: 'index.html')
                }
            }
        }
    }
}
