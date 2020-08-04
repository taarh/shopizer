pipeline {
    agent any

    stages {
        stage ('Initialize for Shopizer') {
                steps {
                sh '''
                    echo "This Jenkinsfile for Building Shopizer Project"
                    echo "PATH = ${PATH}"
                    echo "M2_HOME = ${M2_HOME}"
                    echo "JAVA_HOME = ${JAVA_HOME}"
                    '''
                }
            }
        stage (' Cloning Code base from GIT'){
            steps {
            checkout([$class: 'GitSCM', branches: [[name: '*/refactoring']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[credentialsId: 'be9be694-ee29-4fb5-9bd5-ea491d6a8e2d', url: 'https://github.com/ithelpstream/shopizer.git']]])
        }
        }
        stage ('Build the code using Maven') {
                steps {
                    sh 'mvn clean compile install'
                    }
         }
        stage ('archiveArtifacts for Shopizer'){
            steps {
                archiveArtifacts '**/**/shopizer.war'
            }
        }

    }
}//pipeline