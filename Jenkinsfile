pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                // variable assignment (other than environment variables) can only be done in a script block
                script {
                    result = awsCodeBuild(credentialsId: 'aws-iam-credentials', credentialsType: 'jenkins', projectName: 'JenkinsDemo', region: 'eu-west-2', sourceControlType: 'project')
                    echo "Output: ${result.getArtifactsLocation()}"
                }
            }
        }
        stage('Output') {
            echo "${result.getArtifactsLocation()}"
        }
    }
}
