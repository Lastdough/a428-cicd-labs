node {
    docker.image('node:16-buster-slim').inside('-p 3000:3000') {
        stage('Build') {
            try {
                sh 'npm install'
            } catch (e) {
                currentBuild.result = 'FAILURE'
                throw e
            }
        }
        stage('Test'){
            try {
                sh './jenkins/scripts/test.sh'
            } catch (e) {
                currentBuild.result = 'FAILURE'
                throw e
            }
        }
    }
}