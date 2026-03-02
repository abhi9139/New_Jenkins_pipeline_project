pipeline {
    agent any

    stages {

        stage("Stagea testing") {
            steps {
                catchError(buildResult: 'SUCCESS',stageResult: 'FAILURE'){
                echo "This is linux testing"
                sh '''
                exit 1

                '''
             
            }
        }
        }

           stage("Stageb testing") {
            steps {
                try(){
                
                echo "This is linux testing"
                sh '''
                exit 1

                '''
                }
                catch(err){
                    echo "Error catched :${err}"
                    currentBuild.result="SUCCESS"

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