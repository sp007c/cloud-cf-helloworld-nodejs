@Library ('piper-lib-os') _
node() {
  triggers {
      // Once a minute
      pollSCM('* * * * *')
  }
  stage('prepare'){
    checkout scm
    setupCommonPipelineEnvironment script:this
  }

  stage('build') {
    mtaBuild script: this
  }

  stage('deploy') {
    cloudFoundryDeploy script: this
  }
}
