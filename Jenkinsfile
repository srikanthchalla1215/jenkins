pipeline {
    agent {
        node {
            label 'ROBOSHOP'
        }
    }
        stages {
            stage('build') {
                steps {
                    script{
                        sh """
                           echo "this is hybrid script, this is build phase"
                           exit 1
                        """
                    }
                }
            }

            stage('Test') {
                steps {
                    script{
                        sh """
                            echo "test stage"
                            echo "this is executing stage"
                        """

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