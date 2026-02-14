stage('Deploy') {
    steps {
        sshagent(['web-server-ssh']) {
            sh '''
            scp -o StrictHostKeyChecking=no index.html ec2-user@172.31.11.216:/var/www/html/index.html
            ssh -o StrictHostKeyChecking=no ec2-user@172.31.11.216 "sudo systemctl restart httpd"
            '''
        }
    }
}
