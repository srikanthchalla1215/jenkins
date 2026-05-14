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
        text(name: 'BIOGRAPHY', defaultValue: ' hello srikanth ', description: 'Enter bio details here')
        booleanParam(name: 'TOGGLE', defaultValue: true, description: 'Toggle this value')
        choice(name: 'CHOICE', choices: ['One', 'Two', 'Three'], description: 'Pick something')
        password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'Enter a password') 

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
                echo "TOGGLE: ${params.TOGGLE}"   
                echo "CHOICE is: ${params.CHOICE}"
                echo "PASSWORD is: ${params.PASSWORD}"
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