pipeline {
    agent any
    tools {
        nodejs 'NodeJS-Latest'  // Matches the name you gave
    }
    parameters {
        choice(name: 'ENVIRONMENT', choices: ['dev', 'staging', 'prod'], description: 'Select environment')
    }
    stages {
        stage('Run Postman Tests') {
            steps {
                sh 'newman --version'
                sh """
                newman run postpostcodes.io_collection.json -e ${ENVIRONMENT}_environment.json.json -r cli,html --reporter-html-export output/report.html --bail
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
