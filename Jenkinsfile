pipeline{
    agent any
    environment{
        NEW_VERSION="1.3.0"
    }
    stages{
        stage("compile"){
            steps{
                script{
                    echo "compiling the code"

                }

        }
        }
        stage("test"){
            steps{
                script{
                    echo "testing the code"

                }

            }
            post{
                always{
                    echo "testing is completed"

                }
                
            }

        }
        stage("package"){
            steps{
                script{
                    echo "packaging the code ${NEW_VERSION}"

                }

            }

        }
    }
}
