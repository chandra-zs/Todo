pipeline{
    agent any
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
            curl -f -v -u admin:admin123 --upload-file todo.zip http://3.238.184.24:8081/repository/Todo/todo.zip
            '''
                }


            }
        }
    }
