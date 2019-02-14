pipeline {
    agent any

    stages {
        stage('Setup Virtual Environment'){
            steps {
                sh 'printenv && python3 -m venv ${WORKSPACE}/venv && source ${WORKSPACE}/venv/bin/activate && printenv'
            }
        }
    }
    post {
        always {
            echo "Remove something... "
            //sh 'conda remove --yes -n ${BUILD_TAG} --all'
        }
        failure {
            echo "Send e-mail, when failed"
        }
    }
}