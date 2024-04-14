pipeline{
   agent { 
    label 'linux'
    }
    environment {
        DOCKER_IMAGE = 'ajdevopssolutions/nodejs-hello-world:latest'
    }

    stages {
        stage('Build'){
            steps{
                script {
                    docker.build(env.DOCKER_IMAGE)
                }
            }
        }
        // stage('Test'){
        //     steps{
        //         sh 'docker run ${DOCKER_IMAGE} npm test'
        //     }
        // }
        stage('Deploy'){
            steps{
                script {
                    sh 'kubectl get nodes'
                    sh 'kubectl apply -f ./deployment.yaml'
                }
            }
        }
    }
 
}