pipeline {
    agent any
    parameters {
        credentials(name: 'credentialsId', credentialType: 'CodeBuildCredentials', required: true)
    }
    stages {
        stage('Build') {
            steps {
                // variable assignment (other than environment variables) can only be done in a script block
                script {
                    result = awsCodeBuild(credentialsId: '${params.credentialsId}', credentialsType: 'jenkins', projectName: 'JenkinsDemo', region: 'eu-west-2', sourceControlType: 'project')
                    echo "Output: ${result.getArtifactsLocation()}"
                }
            }
        }
        stage('Output') {
            steps {
                echo "${result.getArtifactsLocation()}"
            }
        }
    }
}
