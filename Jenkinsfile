pipeline{
    agent any

    stages{
        stage("Install dependencies"){
            when{
                branch "main"
            }
            steps{
                echo "dotnet restore"
            }
            post{
                success{
                    echo "========Install dependencies executed successfully========"
                }
                failure{
                    echo "========Install dependencies execution failed========"
                }
            }
        }
        stage("Build application"){
            when{
                branch "main"
            }
            steps{
                echo "dotnet build --no-restore"
            }
            post{
                success{
                    echo "========Build application executed successfully========"
                }
                failure{
                    echo "========Build application execution failed========"
                }
            }
        }
        stage("Run tests"){
            when{
                branch "main"
            }
            steps{
                echo "dotnet test --no-restore --no-build"
            }
            post{
                success{
                    echo "========Run tests executed successfully========"
                }
                failure{
                    echo "========Run tests execution failed========"
                }
            }
        }
    }
    post{
        success{
            echo "========pipeline executed successfully ========"
        }
        failure{
            echo "========pipeline execution failed========"
        }
    }
}