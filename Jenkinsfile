def repo="https://ynserdgn.github.io/helm-repo/"
pipeline {
    agent any
    stages {
        stage("install helm"){
            steps{
                 sh 'wget https://get.helm.sh/helm-v3.6.1-linux-amd64.tar.gz'
                 sh 'ls -a'
                 sh 'tar -xvzf helm-v3.6.1-linux-amd64.tar.gz'
                 sh 'sudo cp linux-amd64/helm /usr/bin'
                 sh 'helm version'
            }
        }
        stage('Hello') {
            steps {
                sh "helm repo add hello-world-2 ${repo}"
            }
        }
    }
}
