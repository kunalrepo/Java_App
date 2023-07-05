@Library('my-shared-library@main')


pipeline{

    agent any 
stages {
    stage('gitCheckout')
    {
        steps{
            script {
                gitCheckout {
                    branch: "main"
                    url: "https://github.com/kunalrepo/Java_App.git"
                }
        }
    }
}
}
}