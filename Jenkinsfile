@Library('piper-lib-os') _

node() {

  stage('prepare') {
      checkout scm
      setupCommonPipelineEnvironment script:this
  }

  stage('build') {
      mtaBuild script: this, dockerImage: 'ppiper/mta-archive-builder', buildTarget: 'NEO'
  }

  stage('deploy') {
      withCredentials([usernamePassword(credentialsId: 'neo-credentials', passwordVariable: '$pass', usernameVariable: '$user')]) {
    sh "echo $user"
}
      neoDeploy script: this, dockerImage: 'ppiper/neo-cli'
  }
}
