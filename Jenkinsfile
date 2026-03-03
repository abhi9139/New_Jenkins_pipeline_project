pipeline{
    agent any
    parameters{
        booleanParam(name:'DEPLOY', description:"Want to deploy parameters")
    }
    environment{
        Name_Env="Prod"
    }

    stages{


        stage("CHECKOUT"){
            steps{
        checkout([$class:'GitSCM',
             branches: [[name: '*/main']],
            extensions: [],
            userRemoteConfigs: [[credentialsId: 'gattu9139', 
            url: 'https://github.com/abhi9139/gattu9139.git'
            ]]
            ])
            }
        }


        stage("Branch Check"){
            when{
             expression{
                return env.GIT_BRANCH=='origin/main'
             }
            }
            steps{
                echo"Params are Checked"
                sh'''
                ls -lrt
                pwd
                echo "Branch is Checked"
                '''


            }
        }

        
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
       
    }
    

}