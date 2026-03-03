pipeline{
    stages{
        stage("This is Linux testing"){
            steps{
                echo "This is linux Testing"
            }
        }

        stage("This is Parallel Testing"){
            parallel(){
                stage("Windows Testing"){
                    steps{
                        sh '''
                        ls -lrt
                        pwd
                        sleep 10
                        '''


                    }



                }
                 stage("Macos Testing"){
                    steps{
                        sh '''
                        ls -lrt
                        pwd
                        sleep 10
                        '''


                    }



                }



            }



        }



        stage("This is final testing"){
            steps{
                echo "This is final stage testing"
            }
        }
    }

}