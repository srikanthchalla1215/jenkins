pipeline {
    agent {
        node {
            label 'ROBOSHOP'
        }
    }

    environment {
        COURSE = 'joindevops'
        DURATION = '3month'
    }
    options {
        disableConcurrentBuilds()
    }

    stages {
        stage('build') {
            steps {
                script{
                    sh """
                        echo "this is hybrid script, this is build phase"
                        echo "duration: ${DURATION}"
                        echo "COURSE is: ${COURSE}"
                        
                    """
                }
            }
        }

        stage('Test') {
            steps {
                script{
                echo "duration: ${DURATION}"
                echo "COURSE is: ${COURSE}"
                }

                sleep 30

            }
        }

        stage('deploy') {
            steps {
                script{
                    sh """
                        echo "deploy stage"
                        echo "this executing deploy stage"
                    """
                }
            }
        }
        
    }
    post {
            always{
                echo 'I will always say Hello again!'
            }
            success{
                echo 'this build is  success'
            }
            failure{
                echo 'pipeline failed please check the logs'
            }
        }
    
}