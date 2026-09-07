@Library('shared') _ 
pipeline {
    agent {label 'shanu'}

    stages {
        stage('Hello') {
            steps {
                script{
                    hello()
                }
            }
        }
        stage('clone') {
            steps {
                script{
                    clone("https://github.com/kumarshanu3355/node-todo-cicd.", "master")
                }
            }
        }
        stage('build') {
            steps {
                script{
                    build("todo-image", "latest")
                }
            }
        }
        stage('DockerPush') {
            steps {
                script{
                    docker_push("todo-image", "latest", "kumarshanu3355")
                }
            }
        }
        stage('Deploy') {
            steps {
                script{
                    deploy("todo-image", "latest", "8000", "todo-cont")
                }
            }
        }
    }
}
