pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                git url: 'https://github.com/Sawaira-Zahra/django-todo-cicd.git', branch: 'main'
            }
        }
        stage('Build') {
            steps {
                echo 'Building..'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying..'
                sshPublisher(
                    publishers: [
                        sshPublisherDesc(
                            configName: 'Install-Jenkins',
                            transfers: [sshTransfer(sourceFiles: '*/', remoteDirectory: '/myapp/')],
                            
                        )
                    ]
                )
            }
        }
    }
