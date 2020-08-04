node{
    stage("SCM Checkout"){
        git 'https://github.com/taarh/shopizer'
    }
    stage("Compile"){
        def mvnHome=tool name: 'maven-3.6.3', type: 'maven'
        sh"${mvnHome}/bin/mvn compile"
    }
}
