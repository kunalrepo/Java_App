@library('my-shared-library') _

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