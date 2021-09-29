pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                bat 'echo "HaHaHa"; exit 1'
            }
        }
    }
    post {
        always {
            echo 'This will always run'
            archiveArtifacts artifacts: 'build/**', fingerprint: true
        }
        success {
            echo 'This will run only if successful'
        }
        failure {
            echo 'This will run only if failed'
        }
        unstable {
            echo 'This will run only if the run was marked as unstable'
        }
        changed {
            echo 'This will run only if the state of the Pipeline has changed'
            echo 'For example, if the Pipeline was previously failing but is now successful'
        }
    }
}
