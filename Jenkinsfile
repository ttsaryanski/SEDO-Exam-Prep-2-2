pipeline{

    agent any

    stages{
        stage("Install dependencies") {
            when {
                expression { return env.GIT_BRANCH == 'origin/main' }
            }
            steps{
                bat "dotnet restore"
            }
        }
        stage("Build application") {
            when {
                expression { return env.GIT_BRANCH == 'origin/main' }
            }
            steps{
                bat "dotnet build --no-restore"
            }
        }
        stage("Run tests") {
            when {
                expression { return env.GIT_BRANCH == 'origin/main' }
            }
            steps{
                bat "dotnet test --no-restore --no-build"
            }
        }
    }
}
