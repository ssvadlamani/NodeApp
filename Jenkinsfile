node {
     stage('SCM Checkout') {
        git url:'https://github.com/ssvadlamani/NodeApp'
    }
     stage('MVN  package') {
         bat "npm install"
      }
      
      stage('Build Docker Image') {
         bat "docker build -t sivasankarvadlamani/nodeapp:2.0.0 ."
      }
       stage('push Docker Image') {
    withCredentials([string(credentialsId: 'docker-pwd', variable: 'dockerHubPwd')]) {
    bat "docker login -u sivasankarvadlamani -p ${dockerHubPwd}" 
}
bat "docker push sivasankarvadlamani/nodeapp:2.0.0"
      }
    
    
}
