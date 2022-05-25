pipeline {
  agent any
  stages {
    stage('git pull') {
      steps {
        // https://github.com/ottogi99/gitops will replace by sed command before RUN
        git url: 'https://github.com/ottogi99/gitops', branch: 'main'
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