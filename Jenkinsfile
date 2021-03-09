pipeline{
    agent {
        label 'master'
    }
    tools {
       jdk 'jdk8'
       maven 'm3'
    }
    stages{
        stage('Checkout SCM'){
            steps{
                checkout scm
            }
        }
        stage('Build FrontEnd'){
            steps{
                sh 'npm install'
                sh 'npm build'
            }

        }
        stage('Build BackEnd'){
            steps{
                sh 'mvn package'
                archiveArtifacts artifacts: 'target/*.war', followSymlinks: false
            }
            
        }

    }
}