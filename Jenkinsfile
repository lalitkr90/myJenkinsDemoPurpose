pipeline {
    agent any
    environment{
        NEW_VRESION = '1.3.0'
        SERVER_CREDENTIALS = credentials('lalit')
    }
    tools{
        maven 'Maven'
    }
    parameters{
        //string(name: 'userName', defaultValue:'', description:'username to be used in UAT')
        choice(name: 'VERSIONS' , choices: ['1.1.0','1.1.2','1.1.3'], description:'')
        booleanParam(name: 'executeTest', defaultValue: true, description:'')
    }
    stages {
        stage('build') {
            steps {
                echo 'This is inside build stage'
                echo 'this is another way of printing'
                echo "Printing environment variable ${NEW_VERSION}"
                sh "mvn install"
            }
        }
        stage('test') {
            when{
                expression {
                    param.executeTest
                }  
            }  
          steps {
             echo 'This is under test stage'
          } 
       }
        stage('deploy'){
            steps {
                echo "This is first variable credential printing ${SERVER_CREDENTIALS}"
                echo "Deploying with parameters ${param.VERSIONS}"
               // withCredetials(SERVER_CREDENTIALS){
                //}
            } 
        } 
    }
}
