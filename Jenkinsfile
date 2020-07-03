pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                sh '''
                . init-build-env
                bitbake core-image-minimal
                '''
            }
        }
    }
}
