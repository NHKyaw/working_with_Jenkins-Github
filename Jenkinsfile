pipeline {
    agent any

    stages {
        stage('Git Pull') {
            steps {
                sh 'cd /var/jenkins_home/workspace/To-Do-App/Jenkins_lab && git pull'
            }
        }

        stage('Build') {
            steps {
                sh 'cd /var/jenkins_home/workspace/To-Do-App/Jenkins_lab && docker build -t getting-started .'
                sh 'docker stop to-do-app'
                sh 'docker run -dp 3000:3000 --name=to-do-app getting-started'
            }
        }
    }
}