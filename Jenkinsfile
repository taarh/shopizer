node{
    def mvnHome=tool name: 'maven-3.6.3', type: 'maven'
    stage("SCM Checkout"){
        git 'https://github.com/taarh/shopizer'
    }
    stage("Test"){
        sh"${mvnHome}/bin/mvn test"
    }
    stage("Compile"){
        sh"${mvnHome}/bin/mvn install  -Dmaven.test.skip=true"
    }
    stage("Build docker image "){
        sh '''
                cd sm-shop
                docker build -f "Dockerfile" -t 0758631838/shopizer-app:1.0.0 .
           '''
    }
    
    stage (" pull Image "){
        withCredentials([string(credentialsId: 'docker-pwd', variable: 'dockerHubPwd')]) {
            sh "docker login -u 0758631838 -p ${dockerHubPwd}"
        }
            sh 'docker push 0758631838/shopizer-app:1.0.0'

    }
}
