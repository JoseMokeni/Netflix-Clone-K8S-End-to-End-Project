pipeline{
    agent any
    tools{
        jdk 'jdk'
        nodejs 'nodejs'
    }
    stages {
        stage('Workspace Cleaning'){
            steps{
                cleanWs()
            }
        }
        stage('Checkout from Git'){
            steps{
                git branch: 'tp', url: 'https://github.com/AmanPathak-DevOpsJoseMokeni/Netflix-Clone-K8S-End-to-End-Project.git'
            }
        }
        stage("Sonarqube Analysis"){
            steps{
                withSonarQubeEnv('sonarqube-server') {
                    sh '''/bin/sonar-scanner -Dsonar.projectName=Netflix \
                    -Dsonar.projectKey=Netflix \
                    '''
                }
            }
        }
    }
}
