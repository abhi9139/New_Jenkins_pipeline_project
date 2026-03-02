pipeline {
    agent any

    stages {

        stage("Linux testing") {
            steps {
                sh '''
                echo "This is linux testing
                exit 1

                '''
             
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