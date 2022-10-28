pipeline {
environment {
registry = "shaisibrahim/project"
registryCredential = 'shaisibrahim'
dockerImage = ''
}
agent any
stages {
stage('Cloning our Git') {
steps {
git 'git clone https://github.com/Remiinisce/Project-TWT.git'
}
}
stage('Building our image') {
steps{
script {
dockerImage = docker.build registry + ":$BUILD_NUMBER"
}
}
}
stage('Deploy our image') {
steps{
script {
docker.withRegistry( '', registryCredential ) {
dockerImage.push()
}
}
}
}
stage('Cleaning up') {
steps{
sh "docker rmi $registry:$BUILD_NUMBER"
}
}
}
}