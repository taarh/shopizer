node{
    stage("SCM Checkout"){
        git 'https://github.com/taarh/shopizer'
    }
    stage("Compile"){
        sh 'mvn compile'
    }
}
