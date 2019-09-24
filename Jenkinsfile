pipeline {
    agent {
        docker { image 'webratio/ant:1.9.6' }
    }

    stages {
        stage('build') {
            steps {
                sh 'ant jar'
            }
        }
        stage('run') {
            steps {
                sh 'ant run'
            }
        }
    }

    post {
        always {
            archiveArtifacts: 'build/*', fingerprint:true
        }
    }
}
