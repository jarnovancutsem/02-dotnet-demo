node {
    stage('Checkout') {
        checkout scm
    }
    stage('Deploy') {
        sh 'docker compose up -d --build'
    }
    stage('Verify') {
        sh 'curl -f --retry 10 --retry-delay 3 --retry-connrefused http://172.16.0.10:8081/'
    }
}