pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building project...'
            }
        }

        stage('Test') {
            steps {
                echo 'Testing project...'
            }
        }
    }

    post {
        always {
            echo 'Generating report...'
            sh 'echo "<h1>Test Report</h1><p>Pipeline finished successfully.</p>" > report.html'

            publishHTML([
                allowMissing: false,
                alwaysLinkToLastBuild: true,
                keepAll: true,
                reportDir: '.',
                reportFiles: 'report.html',
                reportName: 'Test Report'
            ])

            sh 'wkhtmltopdf report.html report.pdf'
        }
    }
}
