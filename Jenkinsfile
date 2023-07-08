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
                params.action == 'create'
                      }
                 }
            steps{
                script{
                    gitCheckout(branch: "main", url: "https://github.com/kunalrepo/Java_App.git")
                }
            }
        }
        stage('Unit Test Maven') {
            when{
            expression{
                params.action == 'create'
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
                params.action == 'create'
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
                params.action == 'create'
                      }
                 }
            steps{
                script{
                    // pass credentials define in staticcode analysis groovy file #shared library
                    def SonarqubecredentialsId = 'sonar-api1'
                   statiCodeAnalysis(SonarqubecredentialsId)
                }
            }
        }
        stage('QualityGate Status: SonarQube') {
            when{
            expression{
                params.action == 'create'
                      }
                 }
            steps{
                script{
                    // pass credentials define in staticcode analysis groovy file #shared library
                    def SonarqubecredentialsId = 'sonar-api1'
                   QualityGateStatus(SonarqubecredentialsId)
                }
            }
        }

        stage('Maven Build: maven') {
            when{
            expression{
                params.action == 'create'
                      }
                 }
            steps{
                script{
                    mavBuild()
                }
            }
        }
    }

}
