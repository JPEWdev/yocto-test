pipeline {
    agent any

    environment {
        PYREX_BIND = '/mnt/yocto-cache'
        BB_ENV_EXTRAWHITE = 'MACHINE'
        SITE = "aws"
    }

    stages {
        stage('Build') {
            parallel {
                stage('qemux86-64') {
                    agent any
                    environment {
                        MACHINE = 'qemux86-64'
                    }
                    steps {
                        sh '''
                        source ./init-build-env
                        bitbake core-image-minimal
                        '''
                    }
                }
                stage('qemuarm64-secureboot') {
                    agent any
                    environment {
                        MACHINE = 'qemuarm64-secureboot'
                    }
                    steps {
                        sh '''
                        source ./init-build-env
                        bitbake core-image-minimal
                        '''
                    }
                }
                stage('rock-pi-4') {
                    agent any
                    environment {
                        MACHINE = 'rock-pi-4'
                    }
                    steps {
                        sh '''
                        source ./init-build-env
                        bitbake core-image-minimal
                        '''
                    }
                }
                stage('tinker-board') {
                    agent any
                    environment {
                        MACHINE = 'tinker-board'
                    }
                    steps {
                        sh '''
                        source ./init-build-env
                        bitbake core-image-minimal
                        '''
                    }
                }
            }
        }
    }
}
