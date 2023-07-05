pipeline{

    agent any 

    stage ('gitCheckout')
    {
        steps{
            script {
                git branch: 'main', url: 'https://github.com/kunalrepo/Java_App.git'
        }
    }
}