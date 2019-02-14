pipeline {
    agent any

    environment {
        VENV_HOME = '${WORKSPACE}/venv'
    }

    stages {
        stage('Setup Virtual Environment'){
            steps {
                sh 'mkdir ${WORKSPACE}/env'
                sh 'python3 -m venv ${WORKSPACE}/env && source ${WORKSPACE}/env/bin/activate'
                //sh 'pip install -r requirements.txt'
            }
        }
        stage('Test environment') {
            steps {
                sh 'python main.py'
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