pipeline {
    agent any
    options {
        timestamps ()
    }

    stages {
        stage("Print ENV"){
            steps {
                echo sh(script:'env|sort', returnStdout: true)
            }       
        }

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