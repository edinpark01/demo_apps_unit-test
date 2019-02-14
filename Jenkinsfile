pipeline {
    agent any

    environment {
        VENV_HOME = '${WORKSPACE}/venv'
    }

    stages {
        stage('Setup Virtual Environment'){
            steps {
                sh 'python3 -m venv ${WORKSPACE}/venv && source ${WORKSPACE}/venv/bin/activate'
                sh 'printenv'
                //sh 'pip install -r requirements.txt'
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