def repoName="test_helm_repo"
def repoUrl="https://ynserdgn.github.io/helm-repo/"
def appName="charts/hello_world"
pipeline {
    agent any
    stages {
       /*stage("install helm"){
            steps{
                 sh 'wget https://get.helm.sh/helm-v3.6.1-linux-amd64.tar.gz'
                 sh 'ls -a'
                 sh 'tar -xvzf helm-v3.6.1-linux-amd64.tar.gz'
                 sh 'sudo cp linux-amd64/helm /usr/bin'
                 sh 'helm version'
            }
        }*/
        stage('helm package') {
            steps {
                sh "helm package ./${appName}"
            }
        }
        stage('helm create index') {
            steps {
                sh "helm repo index ${repoName}/ --url ${repoUrl}"
            }
        }
        stage('Hello') {
            steps {
                sh "helm repo add ${repoName} ${repoUrl}"
            }
        }
    }
}
