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
//                 '''
//             }
//         }

        stage('Install AWS CLI'){
            steps{
                sh '''
                    apt-get update && apt-get install -y sudo
                    # Download and install AWS CLI
                    curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip"
                    unzip -o awscliv2.zip
                    sudo ./aws/install
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