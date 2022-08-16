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
                sh 'docker build -t aesthisia-demo .'
                sh 'docker tag aesthisia-demo:latest aesthisia-demo:${ver1}'
                sh 'docker run -d -it -p 3000:3000 aesthisia-demo:${ver1}'
                               
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
