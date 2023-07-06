@Library('my-shared-library') _

pipeline{
    agent any

    // add parameters
    parameters{
        choice(name: 'action', choices: 'create\ndelete' , description: 'choose create/distroy')
    }

    stages {
       
        stage('gitCheckout') {
            when{
            expression{
                param.action == 'create'
                      }
                 }
            steps{
                script{
                    // this is fetching from shared library grrovy scripts
                    gitCheckout(branch: "main", url: "https://github.com/kunalrepo/Java_App.git")
                }
            }
        }
        stage('Unit Test Maven') {
            when{
            expression{
                param.action == 'create'
                      }
                 }
            steps{
                script{
                    // first install maven inside the jenkins server using maven scrip from install scripts repo
                   mvnTest()
                }
            }
        }
        stage('Integration Test Maven') {
            when{
            expression{
                param.action == 'create'
                      }
                 }
            steps{
                script{
                    
                   mvnIntegrationTest()
                }
            }
        }
         stage('Static Code Analysis: SonarQube') {
            when{
            expression{
                param.action == 'create'
                      }
                 }
            steps{
                script{
                    
                   statiCodeAnalysis()
                }
            }
        }
    }
}
