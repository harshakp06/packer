pipeline {
  agent any
  environment {
    AWS_ACCESS_KEY_ID = credentials('access_key')
    AWS_SECRET_ACCESS_KEY = credentials('aws_secertkey')
  }
  stages {
    stage('packer build') {
      steps {
        sh '''
        packer init aws-ami-v1.pkr.hcl
        packer fmt aws-ami-v1.pkr.hcl
        packer validate aws-ami-v1.pkr.hcl
        packer build aws-ami-v1.pkr.hcl
        '''
      }
    }

  }
}
