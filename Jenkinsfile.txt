pipeline {
    agent any
    stages {
        stage('Restore') {
            steps {
                bat 'dotnet restore HouseRentingSystem.sln'
            }
        }
        stage('Build') {
            steps {
                bat 'dotnet build HouseRentingSystem.sln --configuration Release'
            }
        }
        stage('Test') {
            steps {
                bat 'dotnet test HouseRentingSystem.Tests/HouseRentingSystem.Tests.csproj'
            }
        }
    }
}