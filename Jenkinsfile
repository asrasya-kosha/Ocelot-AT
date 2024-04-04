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
                sh 'dotnet build'
            }
        }
        stage('Run Ocelot Unit Tests'){
            steps{
                sh 'dotnet test --no-build --framework net8.0 --filter "UnitTests"'
            }
        }
        stage('Run Ocelot Integration Tests'){
            steps{
                sh 'dotnet test --no-build --framework net8.0 --filter "IntegrationTests"'
            }
        }
        stage('Run Ocelot Acceptance Tests'){
            steps{
                sh 'dotnet test --no-build --framework net8.0 --filter "AcceptanceTests"'
            }
        }
    }
}
