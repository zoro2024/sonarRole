pipeline {
    agent any
    
    environment {
        AWS_ACCESS_KEY_ID     = credentials('aws_access_key_id')
        AWS_SECRET_ACCESS_KEY = credentials('aws_secret_access_key')
    }
    
    stages {
        stage('Installing SonarQube') {
            steps {
                script {
                    ansiblePlaybook(
                        playbook: 'install.yml',
                        inventory: 'aws_ec2.yaml'
                    )
                }
            }
        }
    }
}
