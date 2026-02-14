pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                git branch: 'main',
                url: 'https://github.com/manmadhdevops/jenkis.git'
            }
        }

        stage('Deploy') {
            steps {
                sh '''
                scp -o StrictHostKeyChecking=no index.html ec2-user@172.31.11.216:/var/www/html/index.html
                ssh -o StrictHostKeyChecking=no ec2-user@172.31.11.216 "sudo systemctl restart httpd"
                '''
            }
        }
    }
}
