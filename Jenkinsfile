pipeline {
    agent any

    environment {
        VENV_HOME = '${WORKSPACE}/venv'
    }

    stages {
        stage('Setup Virtual Environment'){
            steps {
                sh '#!/bin/bash'
                sh 'python3 -m venv ${WORKSPACE}/venv'
                sh 'source ${WORKSPACE}/venv/bin/activate'
                sh 'printenv'
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