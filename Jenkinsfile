pipeline {
  agent {
    kubernetes {
      cloud 'aksdev'
      yamlFile 'kubepod.yaml'
    }
  }
    stages { 
    stage('Deploy Application') {
      steps {
        container('deployer') {
          sh 'ls -al'
          sh "kubectl apply -f frontendapp-dep.yaml"
          sh "kubectl apply -f frontendapp-svc.yaml"          
        }
      }
    }
  }
}