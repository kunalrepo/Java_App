@Library('my-shared-library') _

pipeline{
    agent any

    stages {
        stage('gitCheckout') {
            steps{
                script{
                    // this is fetching from shared library grrovy scripts
                    gitCheckout(branch: "main", url: "https://github.com/kunalrepo/Java_App.git")
                }
            }
        }
        stage('Unit Test Maven') {
            steps{
                script{
                    // first install maven inside the jenkins server using maven scrip from install scripts repo
                   mvnTest()
                }
            }
        }
    }
}
