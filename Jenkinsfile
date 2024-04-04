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
                sh 'dotnet test --no-build --framework net8.0  --filter "UnitTests" --logger:"trx;logfilename=UnitTests.trx"'
            }
        }
        stage('Run Ocelot Integration Tests'){
            steps{
                sh 'dotnet test --no-build --framework net8.0 --filter "IntegrationTests" --logger:"trx;logfilename=IntegrationTests.trx"'
            }
        }
        stage('Run Ocelot Acceptance Tests'){
            steps{
                sh 'dotnet test --no-build --framework net8.0 --filter "AcceptanceTests" --logger:"trx;logfilename=AcceptanceTests.trx"'
            }
        }
    }
    post{
                always {
                    sh ''
                    archiveArtifacts artifacts: '**/TestResults/**/*.trx', fingerprint: true
                }
    }
}
