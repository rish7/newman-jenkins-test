pipeline {
    agent any
    parameters {
        choice(name: 'ENVIRONMENT', choices: ['dev', 'staging', 'prod'], description: 'Select environment')
    }
    stages {
        stage('Run Postman Tests') {
            steps {
                sh """
                newman run collection.json -e ${ENVIRONMENT}.json -r cli,html --reporter-html-export output/report.html
                """
            }
        }
    }
    post {
        always {
            archiveArtifacts artifacts: 'output/*.html', allowEmptyArchive: true
        }
    }
}
