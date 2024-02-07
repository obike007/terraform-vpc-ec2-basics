pipeline {
    agent any

    stages {
//         stage('Checkout') {
//             steps {
//             checkout([$class: 'GitSCM', branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/mydevopscoach/my-tf-iac-aws-repo']]])            

//           }
//         }
        stage ("provider.tf") {
            steps {
                sh (provider "aws" 
                region     = "eu-west-1"
                access_key = "AKIA3KBZTZZMAPPJYX7D"
                secret_key = "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")
            }
        }   
        
        stage ("terraform init") {
            steps {
                sh ('terraform init') 
            }
        }
        
        stage ("terraform Action") {
            steps {
                echo "Terraform action is --> ${action}"
                sh ('terraform ${action} --auto-approve') 
           }
        }
    }
}
