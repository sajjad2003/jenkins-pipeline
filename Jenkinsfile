pipeline {


    environment {

        REACT_APP_VERSION = "1.0.$BUILD_ID"
    }

    stages {

        stage('AWS') {
            agent {
                docker {
                    image 'amazon/aws-cli'
             
                }
            }
  
            steps {
                withCredentials([usernamePassword(credentialsId: 'aws-cre', passwordVariable: 'AWS_SECRET_ACCESS_KEY', usernameVariable: 'AWS_ACCESS_KEY_ID')]) {
                    sh '''
                        aws --version

                    '''
                }
            }
        }
    }
}

