pipeline {
    agent { 
        node {
            label 'docker-agent-python'
            //label 'Built-In-Node'
            }
        }
      triggers {
            pollSCM 'H/2 * * * *'
        }
    stages {
        stage('Build') {
            steps {
                echo "Building.."
                sh '''
                cd myapp
                pip install -r requirements.txt  
                '''
            }
        }
        stage('Test') {
            steps {
                echo "Testing.."
                sh '''
                cd myapp
                python3 hello.py
                python3 hello.py --name=Mateusz
                '''
            }
        }
        stage('Deliver') {
            steps {
                echo "Deliver...."
                sh '''
                echo "doing delivery stuff.."
                '''
            }
        }
    }
}