pipeline{
    agent any

    stages{
//         stage('Build'){
//             agent{
//                 docker{
//                     image 'node:18-alpine'
//                     reuseNode true
//                 }
//             }
//             steps{
//                 sh '''
//                     ls -la
//                     node --version
//                     npm --version
//                     npm ci
//                     npm run build
//                     ls -la
//                 '''
//             }
//         }

//         stage('Installing Sudo'){
//             steps{
//                 sh '''
//                     apt-get update && apt-get install -y sudo
//                     sudo --version
// # apt-get update && apt-get install -y sudo
//                     # Download and install AWS CLI
//                     #curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip"
//                     #unzip -o awscliv2.zip
//                     #./aws/install -b $HOME/.local/bin
//                     #$HOME/.local/bin/aws --version
//                 '''
//             }
//         }

        stage('Install AWS CLI'){
            agent{
                docker{
                    image 'amazon/aws-cli:latest'
                    reuseNode true
                    args '--entrypoint=""'
                }
            }
            steps{
                sh '''
                    aws --version
                '''
            }
        }

        stage('Use AWS CLI'){
            steps{
                sh '''
                    # Configure AWS CLI (example credentials, replace with your actual ones)
                    echo 'AWS CLI is installed successfully!'
                '''
            }
        }
    }
}