def repo="https://ynserdgn.github.io/helm-repo/"
pipeline {
    agent any

    stages {
        stage('Hello') {
            steps {
                sh "helm repo add hello-world ${repo}"
            }
        }
    }
}
