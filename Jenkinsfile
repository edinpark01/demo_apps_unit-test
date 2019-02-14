pipeline {
    agent any

    environment {
      PATH="/var/lib/jenkins/miniconda3/bin:$PATH"
    }

    stages {
        stage('Print Enviroment Variables'){
            steps {
                sh 'printenv'
            }
        }
        stage('Build environment') {
            steps {
                //sh '''conda create --yes -n ${BUILD_TAG} python source activate ${BUILD_TAG} pip install -r requirements.txt '''
            }
        }
        stage('Test environment') {
            steps {
                echo "Test environment"
                //sh 'source activate ${BUILD_TAG} pip list which pip which python'
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