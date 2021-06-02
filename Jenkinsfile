pipeline {
    agent none
    stages {
        stage('build') {
            steps {
                sh 'mvn --version'
            }
        }
        stage('test') {
          steps {
             echo 'This is under test stage'
          } 
       }
    }
}
