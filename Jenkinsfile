pipeline {
    agent {label 't1'}

    stages {
        stage('Git') {
            steps {
                git branch: 'main',
                    url: "https://github.com/Jozicz/DEVOPS1.git"
            }
        }
        
        stage('Pytest test') {
            steps {
                sh 'pytest'
            }
        }
    }
}