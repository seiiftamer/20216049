pipeline {
    agent any
    stages {
        stage('Pull Repository') {
            steps {
                git branch: 'main', url: 'https://github.com/seiiftamer/20216049'
            }
        }
        stage('Set Permissions') {
            steps {
                sh 'chmod +x run_ls.sh'
            }
        }
        stage('Execute Script') {
            steps {
                script {
                    if (isUnix()) {
                        sh './run_ls.sh'
                    } else {
                        bat 'run_ls.bat'
                    }
                }
            }
        }
    }
}
