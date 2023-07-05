@library('my-shared-library') _

pipeline{

    agent any 
stages {
    stage('gitCheckout')
    {
        steps{
            script {
                gitCheckout {
                    branches: "main",
                    url: "https://github.com/kunalrepo/Java_App.git"
                }
        }
    }
}
}
}