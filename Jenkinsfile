pipeline{
        agent any
        stages{
            stage('Clone'){
                steps{
                    sh "git clone https://github.com/Remiinisce/Project-TWT.git"
                }
            }

            stage('Build Docker') {
                steps{
                    sh "docker build -t flask-app"
                }
            }
            stage("Run container"){
                steps{
                    sh "docker run -p 5000:5000 --name flask-app -d flask-app"
                }
            }
        }
}
