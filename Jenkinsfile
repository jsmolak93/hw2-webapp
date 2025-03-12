pipeline {
    agent any  

    environment {
        DOCKER_IMAGE = "jsmolak93/hw2-webapp:latest"
        KUBECONFIG_CRED_ID = "kubeconfig"
    }

    stage('Clone Repository') {
        steps {
            withCredentials([usernamePassword(credentialsId: 'github-credentials', usernameVariable: 'GIT_USER', passwordVariable: 'GIT_PASS')]) {
                sh '''
                    rm -rf hw2-webapp  # Delete existing directory if it exists
                    git clone https://$GIT_USER:$GIT_PASS@github.com/jsmolak93/hw2-webapp.git
                '''
            }
        }
    }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t $DOCKER_IMAGE .'
            }
        }

        stage('Push to DockerHub') {
            steps {
                withDockerRegistry([credentialsId: 'dockerhub-credentials', url: '']) {
                    sh 'docker push $DOCKER_IMAGE'
                }
            }
        }

        stage('Deploy to Kubernetes') {
            steps {
                withCredentials([file(credentialsId: KUBECONFIG_CRED_ID, variable: 'KUBECONFIG')]) {
                    sh '''
                        kubectl apply -f deployment.yaml
                        kubectl apply -f service.yaml
                    '''
                }
            }
        }
    }

    post {
        success {
            echo 'Deployment successful! 🎉'
        }
        failure {
            echo 'Deployment failed! ❌'
        }
    }
}
