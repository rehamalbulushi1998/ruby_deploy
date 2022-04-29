pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh 'ruby build -o sample main.rb'
            }
        }
        stage('Save artifact') {
            steps {
                archiveArtifacts artifacts: 'sample', followSymlinks: false
            }
        }
    }
}
