pipeline {
    agent any
    stages {
        stage ('build docker image') {
            steps {
                sh '/usr/bin/docker image build -t <docker hub pallavi203/jenkinsdemo .'
            }
        }
        stage ('docker login') {
            steps {
                sh 'ehcho dckr_pat_3XIhJIxZnYe6QkVi-gZC2eKKIYQ | /usr/bin/docker login -u pallavi203 --password-stdin'
            }
        }
        stage ('push docker image') {
            steps {
                sh '/usr/bin/docker image push pallavi203/jenkinsdemo'
            }
        }
        stage ('reload docker service') {
            steps {
                sh '/usr/bin/docker service update --image pallavi203/jenkinsdemo --force myservice'
            }
        }

    }
}
