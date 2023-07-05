@library('my-shared-library') _

pipeline{

    agent any 
stages {
    stage('gitCheckout')
    {
        steps{
            script {
                gitCheckout {
                    branches: [[name: 'main']],
                    url: "https://github.com/kunalrepo/Java_App.git"
                }
        }
    }
}
}
}