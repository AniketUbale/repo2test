ipipeline {
    agent {
        label {
            label "built-in"
            customWorkspace "/mnt/reo-2"
        }
    }
    
    stages{
        stage('delete'){
            steps{
                sh "rm -rf /mnt/repo-2/*"
            }
        }
        stage('clone'){
            steps{
                git 'https://github.com/AniketUbale/repo-2.git'
            }
        }
        stage('deploy'){
            steps{
                sh "yum install httpd -y"
                sh "service httpd start"
                sh "cp -r /mnt/reo-2/index.html /var/www/html/"
                sh "chmod -R 777 /var/www/html/index.html"
            }
        }
    }
}
