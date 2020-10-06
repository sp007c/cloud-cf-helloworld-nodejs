@Library ('piper-lib-os') _
node() {
  properties([
    // Once a minute
    pipelineTriggers([pollSCM('* * * * *')])
  ])
  
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
