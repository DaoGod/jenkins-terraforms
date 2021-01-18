properties([pipelineTriggers([githubPush()])])

pipeline {
    agent { 
      docker {
        image 'hashicorp/terraform'
        args  '--entrypoint='
      }
    }
    
    stages {
	stage('Init Terraform directory'){
	   steps {
		sh 'terraform init'
	}
    }
	stage('Plan Terraform code'){
	   steps {
		sh 'terraform plan'
	}
    }
	stage('Apply Terraform code'){
	   steps {
		sh 'terraform apply -auto-approve'
	}
    }
}
