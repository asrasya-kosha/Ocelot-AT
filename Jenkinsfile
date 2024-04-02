pipeline {
agent any
stages {
        stage('Clean Ocelot'){
            steps{
                sh 'dotnet clean'
            }
        }
        stage('Build Ocelot'){
            steps{
                sh 'dotnet Build'
            }
        }
    }
}
