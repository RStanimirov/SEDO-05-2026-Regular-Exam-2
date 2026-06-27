pipeline {
    agent any

    triggers {
        githubPush()
    }

    stages {
        stage('Restore') {
            when {
                branch 'main'
            }
            steps {
                bat 'dotnet restore'
            }
        }

        stage('Build') {
            when {
                branch 'main'
            }
            steps {
                bat 'dotnet build --configuration Release --no-restore'
            }
        }

        stage('Test') {
            when {
                branch 'main'
            }
            steps {
                bat 'dotnet test --configuration Release --no-build'
            }
        }
    }
}
