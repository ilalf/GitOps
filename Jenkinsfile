pipeline {
  agent any
  stages {
    stage('git pull') {
      steps {
        // https://github.com/ilalf/GitOps.git will replace by sed command before RUN
        git url: 'Git-URL', branch: 'main'
      }
    }
    stage('k8s deploy'){
      steps {
        kubernetesDeploy(kubeconfigId: 'kubeconfig',
                         configs: '*.yaml')
      }
    }    
  }
}