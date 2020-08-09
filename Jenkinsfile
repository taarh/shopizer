node{
    def mvnHome=tool name: 'maven-3.6.3', type: 'maven'
    stage("SCM Checkout"){
        git 'https://github.com/taarh/shopizer'
    }
    stage("Test"){
        sh"${mvnHome}/bin/mvn test"
    }
    stage("Compile"){
        sh"${mvnHome}/bin/mvn compile"
    }
    stage("Build docker image "){
        sh 'cd sm-shop docker build -f "Dockerfile" -t 0758631838/shopizer-app:latest .'
    }
}
