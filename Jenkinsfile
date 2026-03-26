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

            // HTML файл
            sh 'echo "<h1>Test Report</h1>" > report.html'

            // PDF
            sh 'wkhtmltopdf report.html report.pdf'
        }
    }
}
