pipeline {

        agent any
        stages {
            stage('Cloning our Git') {
                steps {
                    git "git clone https://github.com/Remiinisce/Project-TWT.git"
                }
            }
            stage('Building our image') {
                steps{
                       sh "docker build image flask-app"
                    }
                }
            }
            stage('Deploy our image') {
                steps{
                    sh "docker run -p 5000:5000 --name flask-app -d flask-app"
                        }
                    }
                }
            stage('Cleaning up') {
                steps{
                    sh "docker rmi flask-app"
      }
 } 