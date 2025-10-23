pipeline{
    agent any
    stages{
        stage("Restore the dependencies"){
            // when { branch pattern: "(main|feature/.*)", comparator: "REGEXP" }
             when { 
                branch: "main" 
            } OR when { 
                branch: "feature/*" 
            }
            steps{
                bat "dotnet restore"
            }
        }
        stage("Build the application"){
            // when {branch pattern: "(main|feature/.*)", comparator: "REGEXP"}
            when { 
                branch: "main" 
            } OR when { 
                branch: "feature/*" 
            }
            steps{
                bat "dotnet build --no-restore"
            }
        }
        stage("Run the tests"){
            // when {branch pattern: "(main|feature/.*)", comparator: "REGEXP"}
             when { 
                branch: "main" 
            } OR when { 
                branch: "feature/*" 
            }
            steps{
                bat "dotnet test --no-build --verbosity normal"
            }
        }
    }
}