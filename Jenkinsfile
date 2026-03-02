pipeline {
    agent any

    stages {

        stage("Linux testing") {
            steps {
                catchError(buildResult: 'SUCCESS',stageResult: 'FAILURE'){
                echo "This is linux testing"
                sh '''
                exit 1

                '''
             
            }
        }
        }

        stage("Parallel Testing") {
            parallel{
                stage("Windows Testing"){
                steps {
                echo "Windows Testing Done"
            
            }
            }
            stage("Macos Testing"){
                steps{
                echo "Macos Testing Done"
                }
            

            }
            }

            
        }

        stage("Final Stage Testing"){
            steps{
            echo "Final Stage Testing Done"
            }
        }
         

    }
}