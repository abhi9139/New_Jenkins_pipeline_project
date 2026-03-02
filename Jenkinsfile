pipeline {
    agent any 

    parameters {
        booleanParam(name: 'DEPLOY', description: 'Want to deploy to production')
    }

    environment {
        CURRENT_ENV = "Prod"
    }

    stages {

        stage("Environment Variable Check") {
            when {
                environment name: 'CURRENT_ENV', value: 'Prod'
            }
            steps {
                echo "This is Environment Variable check stage"
                sleep time: 5, unit: 'SECONDS'
            }
        }

        stage("Parameter Check") {
            when {
                expression { params.DEPLOY == true }
            }
            steps {
                echo "This is Parameter Variable check stage"
                sh '''
                    pwd
                    ls -lrt
                '''
            }
        }

    }
}