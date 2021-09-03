pipeline {
    agent any
    options {
        timestamps ()
    }

    stages {
        stage("Checkout repository"){
            steps {
                git url: 'https://github.com/edanilovets/ci_cd_course.git'
            }       
        }
        stage("Test"){
            steps {
                sh '/usr/local/bin/jenkins-jobs test -r jobs/ > /dev/null'
            }
        }      
    }
}