pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                def result = awsCodeBuild  credentialsId: 'aws-iam-credentials', credentialsType: 'jenkins', projectName: 'JenkinsDemo', region: 'eu-west-2', sourceControlType: 'project'
                echo "Output: ${result.getArtifactsLocation()}"
            }
        }
    }
}
