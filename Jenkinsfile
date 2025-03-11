pipeline {
    agent any

    stages {
        stage('Check Branch') {
            when {
                expression { env.BRANCH_NAME == 'main' }
            }
            steps {
                echo 'Branch saat ini adalah main, lanjutkan pipeline...'
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
