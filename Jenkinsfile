pipeline{
    agent any
    stages {
        stage(' Docker login') {
            steps {
                sh "aws ecr get-login-password --region us-east-2 | docker login --username AWS --password-stdin 686684895767.dkr.ecr.us-east-2.amazonaws.com"
            }
        }
        stage('build Docker Image') {
            steps {
                sh 'docker build -t ecr-repo-krima .'
                sh "docker tag ecr-repo-krima:latest 686684895767.dkr.ecr.us-east-2.amazonaws.com/ecr-repo-krima:latest"
                sh "docker push 686684895767.dkr.ecr.us-east-2.amazonaws.com/ecr-repo-krima:latest"
            }
        } 
    }
}



// pipeline{
//     agent any
//     stages {
//         stage('Build Docker Image') {
//             steps {
//                 sh "echo staring build the image"
//                 sh 'docker build -t krimavyas/gitops:latest .'
//             }
//         }
//         stage('Deploy Docker Image') {
//             steps {
//                 sh "echo staring deploy the image"
//                 sh 'docker login -u $DOCKER_USERNAME -p $DOCKER_PASSWORD'
//                 sh 'docker push krimavyas/gitops:latest'
//             }
//         }
       
//     }
// }
