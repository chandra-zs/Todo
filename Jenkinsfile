pipeline{
    agent {
     label 'NODEJS'
    }
    stages {
        stage('Download Dependencies') {
            steps {
                sh '''
                npm install
            '''
            }
        }
        stage('prepare Artifacts') {
            steps {
                sh '''
                zip -r todo.zip *
            '''
            }
        }
        stage('upload Artifacts') {
            steps {
                sh '''
            curl -f -v -u admin:admin123 --upload-file todo.zip http://172.31.15.247:8081/repository/todo/todo.zip
            '''
                }


            }
        }
    }
