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
    
    parameters {
        string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')
        text(name: 'BIOGRAPHY', defaultValue: '', description: 'Enter bio details here')

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
                echo "hello ${params.PERSON}"
                echo "hey: ${params.BIOGRAPHY}"
                }

            

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