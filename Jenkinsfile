pipeline {
    agent any

    environment {
        SSH_PRIVATE_KEY = credentials('ssh-private-key-id')
    }

    stages {
        stage('Check Branch') {
            when {
                expression { env.BRANCH_NAME == 'main' }
            }
            steps {
                echo 'Branch saat ini adalah main, lanjutkan pipeline...'
            }
        }

        stage('Setup SSH Key') {
            when {
                expression { env.BRANCH_NAME == 'main' }
            }
            steps {
                script {
                    sh '''
                    mkdir -p ~/.ssh
                    chmod 700 ~/.ssh
                    echo "$SSH_PRIVATE_KEY" > ~/.ssh/id_rsa
                    chmod 600 ~/.ssh/id_rsa
                    '''
                }
            }
        }

        stage('Build') {
            when {
                expression { env.BRANCH_NAME == 'main' }
            }
            steps {
                echo 'Building project...'
                // Tambahkan perintah build, misalnya:
                // sh 'mvn clean package'
            }
        }

        stage('Test') {
            when {
                expression { env.BRANCH_NAME == 'main' }
            }
            steps {
                echo 'Running tests...'
                // Tambahkan perintah test
            }
        }

        stage('Deploy') {
            when {
                expression { env.BRANCH_NAME == 'main' }
            }
            steps {
                echo 'Deploying to production...'
                // Tambahkan perintah deploy
            }
        }
    }
}
