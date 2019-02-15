pipeline {
    agent any

    stages {
        stage('Setup Virtual Environment'){
            steps {
                sh '''
                python3 -m venv ${WORKSPACE}/venv
                '''
            }
        }
        stage('Print Environment Variables'){
            steps {
                sh ''' source ${WORKSPACE}/venv/bin/activate
                        python main.py
                    '''
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