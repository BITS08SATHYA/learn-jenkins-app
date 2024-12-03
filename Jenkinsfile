pipeline{
    agent any

    stages{
        stage('Build'){
            agent{
                docker{
                    image 'node:18-alpine'
                    reuseNode true
                }
            }
            steps{
                sh '''
                    ls -la
                    node --version
                    npm --version
                    npm ci
                    npm run build
                    ls -la
                '''
            }
        }

        stage('Install AWS CLI'){
            steps{
                sh '''
                    # Download and install AWS CLI
                    curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip"
                    unzip awscliv2
                    sudo ./aws/install
                    aws --version
                '''
            }
        }

        stage('Use AWS CLI'){
            steps{
                sh '''
                    # Configure AWS CLI (example credentials, replace with your actual ones)
                    echo 'Working cool'
                '''
            }
        }










    }


}