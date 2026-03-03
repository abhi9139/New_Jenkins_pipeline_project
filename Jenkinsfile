pipeline{
    agent any
    parameters{
        booleanParam(name:'DEPLOY', description:"Want to deploy parameters")
    }
    environment{
        Name_Env="Prod"
    }

    stages{
        stage("Environment variable check"){
            when{
                environment name:"Name_Env",value:"Prod"
            }
            steps{
                echo"Environment Variable is Checked"
                sh '''
                ls -lrt
                pwd
                sleep 5
                '''

            }
        }

        stage("Parametres Check"){
            when{
                expression {params.DEPLOY==true}
            }
            steps{
                echo"Params are Checked"
                sh'''
                ls -lrt
                pwd
                '''


            }
        }
        stage("Branch Check"){
            when{
               any of{
                branch "main"
                environment name:"Name_env",value:"Prod"
               }
            }
            steps{
                echo"Params are Checked"
                sh'''
                ls -lrt
                pwd
                '''


            }
        }
    }
    

}