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
                git branch: "${BRANCH_NAME}", url: 'https://github.com/edanilovets/ci_cd_course.git'
            }       
        }
        stage("Test"){
            steps {
                sh '/usr/local/bin/jenkins-jobs test -r jobs/ > /dev/null'
            }
        }   
        stage("Update JJB"){
            when { branch 'master' }
            // when { environment name: 'BRANCH_NAME', value: 'master'}
            steps {
                sh '/usr/local/bin/jenkins-jobs --conf ./jenkins_jobs.ini update -r jobs/'
            }
        }    
    }
}