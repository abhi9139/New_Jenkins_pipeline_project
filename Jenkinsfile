pipeline {
    agent any

    stages {

        stage("Linux testing") {
            steps {
                sh 'sleep 5'
                echo "This is Linux Testing"
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