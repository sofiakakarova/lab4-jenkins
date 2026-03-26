pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building project...'
            }
        }
post {
    always {
        echo 'Generating report...'
        sh 'echo "<h1>Test Report</h1>" > report.html'
    }
}
        stage('Test') {
            steps {
                echo 'Testing project...'
            }
        }
    }
}
