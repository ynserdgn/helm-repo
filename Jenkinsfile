def repoName="last_repo"
def repoUrl="https://ynserdgn.github.io/helm-repo/"
def appName="hello-world"
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
        stage('helm create chart') {
            steps {
                sh "helm create ./helm-last/${appName}"
            }
        }
        stage('helm Lint') {
            steps {
                sh "helm lint ./helm-last/${appName}"
            }
        }
        stage('helm template') {
            steps {
                sh "helm template ./helm-last/${appName}"
            }
        }
        
        stage('helm package') {
            steps {
                /*sh "pwd"
                dir('helm-last') {
                  sh "pwd"
                }*/
                sh "helm package .helm-last/${appName}"
            }
        }
        stage('helm create index') {
            steps {
                sh "helm repo index ${repoName}/ --url ${repoUrl}"
            }
        }
        stage('helm repo add') {
            steps {
                sh "helm repo add ${repoName} ${repoUrl}"
            }
        }
    }
}
