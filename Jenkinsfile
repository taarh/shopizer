node{
    stage("SCM Checkout"){
        git 'https://github.com/taarh/shopizer.git'
    }
    stage("Compile"){
        sh 'mvn compile'
    }
}
