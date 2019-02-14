pipeline {
    agent any

    environment {
        VENV_HOME = '${WORKSPACE}/venv'
    }

    stages {
        stage('Print Enviroment Variables'){
            steps {
                sh 'printenv'
            }
        }
        stage('Setup Virtual Environment'){
            steps {
                sh '$VENV_HOME'
                sh 'python3 -m venv $VENV_HOME && source $VENV_HOME/bin/activate'
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