# JenkinAssignment2

pipeline {
 agent any
 environment {
  dotnet = 'C:/Program Files (x86)/dotnet/dotnet.exe'
 }
 stages {
  stage('Checkout') {
   steps {
    git url: 'https://github.com/ManankGupta1509/JenkinAssignment2.git', branch: 'main'
   }
  }
    stage('Restore PACKAGES'){
        steps{
            bat "dotnet restore JenkinAssignment2.sln"
        }
    }  
  stage('Build') {
   steps {
    bat 'dotnet build --configuration Release'
   }
  }
 }
}
