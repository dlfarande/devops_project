pipeline {
environment {
registry = "dockerhub registry name"
registryCredential = 'dockerhubcredentials'
dockerImage = ''
}
agent any
stages {
stage('Checkout') {
steps {
git credentialsId: '777a7344-89b9-4515-9830-3bd6e9a66158', url:
'https://github.com/yourrepository.git'
}
}
stage('Docker Build') {
steps{
script {
dockerImage = docker.build registry + ":Login-Form-$BUILD_NUMBER"
}
}
}
stage('Docker Push') {
steps{
script {
docker.withRegistry( '', registryCredential ) {
dockerImage.push()
}
}
}
}
}
}
