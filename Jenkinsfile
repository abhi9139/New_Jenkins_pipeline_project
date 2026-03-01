pipeline {
    agent any

    stages {

        stage("STAGE1") {
            steps {
                sh 'sleep 5'
                echo "This is Stage one"
            }
        }

        stage("STAGE2") {
            steps {
                sh '''
                #!/bin/bash
                pwd
                ls -lrt
                echo "This is Stage two"
                '''
            }
        }

    }
}