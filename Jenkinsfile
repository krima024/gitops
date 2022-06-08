pipeline{
    agent any
    stages {
        stage('Build Docker Image') {
            steps {
                sh "echo staring build the image"
                sh 'docker build -t krimavyas/gitops:latest .'
            }
        }
        stage('Deploy Docker Image') {
            steps {
                sh "echo staring deploy the image"
                sh 'docker login -u $DOCKER_USERNAME -p $DOCKER_PASSWORD'
                sh 'docker push krimavyas/gitops:latest'
            }
        }
       
    }
}
