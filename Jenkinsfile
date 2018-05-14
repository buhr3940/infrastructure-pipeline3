properties([pipelineTriggers([githubPush()])])
node('linux') {
    git url: 'https://github.com/buhr3940/infrastructure-pipeline3.git', branch: 'master'
    stage('Test') {
        sh "env"
    }
}
