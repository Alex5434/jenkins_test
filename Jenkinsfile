
pipeline {
    agent { 
        node {
            label 'docker_python_agent'
            }
      }
    triggers {
        pollSCM '* * * * *'
    }
    stages {
        stage('Build') {
            steps {
                echo "Building.."
                sh '''
                echo "doing build stuff.."
                '''
            }
        }
        stage("Parallel Stage"){
            parallel{
                stage('Test') {
                    steps {
                        echo "Testing..1"
                        sh '''
                        echo "doing test stuff..1"
                        '''
                    }
                }
                stage('Test1') {
                    steps {
                        echo "Testing..1"
                        sh '''
                        echo "doing test stuff..1"
                        '''
                    }
                }
            }
        }
        stage('Deliver') {
            steps {
                echo 'Deliver....'
                sh '''
                echo "doing delivery stuff.."
                '''
            }
        }
    }
}