pipeline {
  agent {
    docker {
      image 'hashicorp/terraform:light'
      args '--entrypoint='
    }

  }
  stages {
    stage('Init') {
      steps {
        sh 'terraform init -backend-config=backend.tfvars'
      }
    }

    stage('Plan') {
      steps {
        sh 'terraform plan'
      }
    }

<<<<<<< HEAD
    options {
       withCredentials([[$class: 'AmazonWebServicesCredentialsBinding', accessKeyVariable: 'AWS_ACCESS_KEY_ID', credentialsId: 'ynov_15', secretKeyVariable: 'AWS_SECRET_ACCESS_KEY']])	
=======
    stage('Apply') {
      steps {
        sh 'terraform apply -auto-approve'
      }
    }

    stage('Output') {
      steps {
        sh 'terraform output'
      }
>>>>>>> 1e04fe106c9b13aa91985c040d0f2fad28d12b8c
    }

  }
  environment {
    AWS_REGION = 'eu-west-3'
  }
  options {
    withCredentials([[$class: 'AmazonWebServicesCredentialsBinding', accessKeyVariable: 'AWS_ACCESS_KEY_ID', credentialsId: 'ynov_15', secretKeyVariable: 'AWS_SECRET_ACCESS_KEY']])
  }
}