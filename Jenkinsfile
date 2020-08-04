node{
    def mvnHome=tool name: 'maven-3.6.3', type: 'maven'
    stage("SCM Checkout"){
        git 'https://github.com/taarh/shopizer'
    }
     stage("TEST"){
        sh "${mvnHome}/bin/mvn test"
    }
    stage("Compile"){
        sh "${mvnHome}/bin/mvn compile"
    }
   
}
