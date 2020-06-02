pipeline {
   agent any
   stages {   
		stage('SCM Git Checkout') {
		 steps {
				git credentialsId: 'xxxx', url: 'https://github.com/arindam-b/aws-terraform-cloudwatch-jenkins-pipeline.git'
				}
		}

        stage('terraform'){
            steps {
					withCredentials([[
						$class: 'AmazonWebServicesCredentialsBinding',
						credentialsId: 'AWS_CREDENTIALS_TERRAFORM_INSTALL',
						accessKeyVariable: 'AWS_ACCESS_KEY_ID',
						secretKeyVariable: 'AWS_SECRET_ACCESS_KEY'
					  ]])
						{
						sh '''
							rm provider.tf
							sed -e 's/aws_access_key/'${AWS_ACCESS_KEY_ID}'/' -e 's/aws_secret_key/'${AWS_SECRET_ACCESS_KEY}'/' -e 's/aws_region/us-east-1/' aws_provider.tf > provider.tf
							rm aws_provider.tf							
							terraform init  --input=false
							terraform plan  -out myplan
							terraform apply "myplan"
							'''
						}
				  }
			}
		}
}		