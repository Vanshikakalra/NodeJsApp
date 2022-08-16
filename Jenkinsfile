pipeline {
    agent any
    parameters {
        string(name: "ver1", defaultValue: "vans", trim: true, description: "tag parameter")
    }
    stages {
        stage("Build") {
            steps {
                echo "Build stage."
                echo "Hello $params.ver1"
                sh 'docker run -d -it -p 3002:3002 -f dockerfile.dev'
                sh 'docker tag aesthisia-demo:latest aesthisia-demo:${ver1}'

            }
        }
        stage("Test") {
            steps {
                echo "Test stage."
            }
        }
        stage("Release") {
            steps {
                echo "Release stage."
            }
        }
    }
}
