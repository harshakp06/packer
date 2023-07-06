pipeline {
  agent any
  stages {
    stage('packer installation'){
      steps{
        sh '''
        curl -fsSL https://apt.releases.hashicorp.com/gpg | sudo apt-key add -
        sudo apt-add-repository "deb [arch=amd64] https://apt.releases.hashicorp.com $(lsb_release -cs) main"
        sudo apt-get update && sudo apt-get install packer
        '''
      }  
    }
    stage('packer build') {
      steps {
        sh '''
        packer init .
        packer fmt .
        packer validate .
        packer build aws-ami-v1.pkr.hcl
        '''
      }
    }

  }
}
