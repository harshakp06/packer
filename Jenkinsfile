pipeline {
  agent any
  stages {
    stage('packer build') {
      steps {
        sh 'packer init .'
        sh '''packer fmt .
'''
        sh 'packer validate .'
        sh 'packer build aws-ami-v1.pkr.hcl'
      }
    }

  }
}