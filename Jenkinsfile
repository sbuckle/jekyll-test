pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                awsCodeBuild  credentialsId: 'aws-iam-credentials', projectName: 'JenkinsDemo', region: 'eu-west-2', sourceControlType: 'project'
            }
        }
    }
}
