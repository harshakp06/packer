pipeline {
  agent any
  stages {
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
