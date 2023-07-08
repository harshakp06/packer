pipeline {
  agent any
  
  stages {
    stage('hello'){
      steps{
        sh 'echo packer build'
      }
    }
    stage('packer build') {
      steps {
        withCredentials([<object of type com.cloudbees.jenkins.plugins.awscredentials.AmazonWebServicesCredentialsBinding>]) {
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
}
