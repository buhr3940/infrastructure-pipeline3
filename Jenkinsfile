properties([pipelineTriggers([githubPush()])])
node('linux') {
    git url: 'https://github.com/buhr3940/infrastructure-pipeline3.git', branch: 'master'
    stage('Test') {
        sh "env"
    }
    stage ("GetInstances") {

    sh "aws ec2 describe-instances --region us-east-1"
        
    }

    stage ("CreateInstance") {
    // TODO
        withCredentials([[$class: 'AmazonWebServicesCredentialsBinding', accessKeyVariable: 'AWS_ACCESS_KEY_ID', credentialsId: 'buhr3940', secretKeyVariable: 'AWS_SECRET_ACCESS_KEY']]) {
            sh "aws ec2 run-instances --image-id ami-467ca739 --count 1 --instance-type t2.micro --key-name classroom --security-group-ids sg-07e05871 --subnet-id subnet-9fc7c4d4  --region us-east-1"
        }
    }
}
