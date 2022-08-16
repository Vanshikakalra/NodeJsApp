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
                sh 'sudo docker build - < dockerfile.dev'
                sh 'sudo docker run aesthisia-demo -p 3000:3000'
                sh 'sudo docker tag aesthisia-demo:latest aesthisia-demo:${ver1}'
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
