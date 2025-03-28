pipeline {
    agent {label 't1'}

    stages {
        stage('checkout') {
            steps {
                git branch: 'main',
                    url: "https://github.com/Jozicz/DEVOPS1.git"
            }
        }

        stage('run tests') {
            steps {
                sh 'pytest'
            }
        }

        stage('Deploy') {
            when {
                expression {
                    currentBuild.result == null || currentBuild.result == 'SUCCESS'
                }
            }
            steps {
                echo 'docker build -t moja-apka . && docker push moja-apka'
            }
        }
    }
    post {
        failure {
            echo 'Testy nieudane'
        }
        success {
            echo 'Aplikacja zdeployowana'
        }
    }
}
