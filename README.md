1. In to jenkins install cloudbees aws plugins
2. install terraform into the jenkins server
	sudo apt-get install unzip
	wget https://releases.hashicorp.com/terraform/0.12.7/terraform_0.12.7_linux_amd64.zip
	unzip terraform_0.12.7_linux_amd64.zip
	sudo mv terraform /usr/local/bin/
	terraform --version 
3. Install aws cli
	curl "https://d1vvhvl2y92vvt.cloudfront.net/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip"
	unzip awscliv2.zip
	sudo ./aws/install
	sudo apt install awscli
4. Add aws credentials from credential details
	refer screen shots
5. Update Jenkinsfile and build	

for aws services:

install aws plugins: 	
Pipeline: AWS Steps

Refer screen shots