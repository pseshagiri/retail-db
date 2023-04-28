pipeline{
    agent any
    stages{
        stage("Execute Secret file"){
         steps{
           script{
               kubeconfig(credentialsId:'minikubeconfig',serverUrl:'http://192.168.49.1:8443') {
                  sh  'kubectl apply -f ./mysql-secret.yaml'   
               }
             }               
           }                   
        }
        stage("Execute Storage file"){
         steps{
         	script{
               kubeconfig(credentialsId:'minikubeconfig',serverUrl:'http://192.168.49.1:8443') {
                  sh 'kubectl apply-f mysql-storage.yaml'   
               }
             } 
                             
        }
    }
    stage("Execute Deployment file"){
      steps{
        script{
               kubeconfig(credentialsId:'minikubeconfig',serverUrl:'http://192.168.49.1:8443') {
                  sh 'kubectl apply -f mysql-deployment.yaml'   
               }
             }        
      }                   
    }
  }//stages  
}//pipeline
