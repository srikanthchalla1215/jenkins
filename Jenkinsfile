pipeline {
    agent any 
        stages {
            stage('build') {
                steps {
                    script{
                        sh """
                           echo "this is hybrid script, this is build phase"
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
    
}