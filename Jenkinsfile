pipeline {
    agent any

    stages {
        stage ('SCM') {
            steps {
                git 'https://github.com/C2-80405/lab-exam.git'
            }
        }
        stage ('docker login') {
            steps {
                sh 'echo dckr_pat_3XIhJIxZnYe6QkVi-gZC2eKKIYQ | /usr/bin/docker login -u pallavi203 --password-stdin'
            }
        }
        stage ('docker build image') {
            steps {
                sh '/usr/bin/docker build -t pallavi203/mywebsite .'
            }
        }
        stage ('docker image push') {
            steps {
                sh '/usr/bin/docker push pallavi203/mywebsite'
            }
        }
        stage ('docker remove service') {
            steps {
                sh '/usr/bin/docker service rm myservice'
            }
        }
        stage ('docker create service') {
            steps {
                sh '/usr/bin/docker service create --name myservice -p 9876:80 --replicas 5 pallavi203/mywebsite'
            }
        }
    }
}
