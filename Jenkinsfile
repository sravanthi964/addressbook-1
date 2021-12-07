pipeline{
    agent any
    tools{
        maven "mymaven"
        jdk "myjava"
    }
    parameters{
        string( name: "VERSION",defaultValue: "",description: "version to deploy")
        choice(name: "version", choices:["1.1.0","1.2.0","1.3.0"])
        booleanParam(name: "executeTests",defaultValue: true,description: "Testcases")
    }
    environment{
        NEW_VERSION="1.3.0"
    }
    stages{
        stage("compile"){
            steps{
                script{
                    echo "compiling the code"
                    sh "mvn compile"

                }

        }
        }
        stage("test"){
            steps{
                script{
                    echo "testing the code"
                    sh "mvn test"

                }

            }
            post{
                always{
                    junit "target/surefire-reports/*.xml"
                    echo "testing is completed"

                }
                
            }

        }
        stage("package"){
            when{
                expression{
                    params.executeTests== true
                }
            }
            steps{
                script{
                    echo "packaging the code ${NEW_VERSION}"
                    sh "mvn package"

                }

            }

        }
    }
}
