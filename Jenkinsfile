pipeline {
    agent none
    stages {
        stage("Build"){
            agent {
        node{
            label "linux && java17"
        }
    }
            steps {

                script {
                    def data = [
                        "firstName": "Miftahul",
                        "lastName": "Khannedy"
                    ]
                    writeJSON(file: "data.json", json:)
                }

                script {
                    for (int i = 0; i < 10; i++){
                    echo("Script ${i}")
                    }
                }
                echo("Start Build")
                sh("./mvnw clean compile test-compile")
                echo("Finish Build")
            }
        }

        stage("Test"){
            agent {
        node{
            label "linux && java17"
        }
    }
            steps {
                echo("Start Test")
                sh("./mvnw test")
                echo("Finish Test")
            }
        }

        stage("Deploy"){
            agent {
        node{
            label "linux && java17"
        }
    }
            steps {
                echo("Hello Deploy 1")
                sleep(5)
                echo("Hello Deploy 2")
                echo("Hello Deploy 3")
            }
        }

    }
    post{
        always{
            echo "I will always say Hello again!"
        }
        success{
            echo "Yay, success"
        }
        failure{
            echo "Oh no, failure"
        }
        cleanup{
            echo "Don't care success or error"
        }
    }
}
    