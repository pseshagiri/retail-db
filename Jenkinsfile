pipeline{
    agent any
    stages{
        stage("Execute Secret file"){
         steps{
               script{
                sh  'kubectl apply -f mysql-secret.yaml'
               }
           }                   
        }
        stage("Execute Storage file"){
         steps{
               script{
                sh 'kubectl apply-f mysql-storage.yaml'
           }                   
        }
    }
    stage("Execute Deployment file"){
      steps{
          script{
     		sh 'kubectl apply -f mysql-deployment.yaml'
	   }        
      }                   
    }
  }//stages  
}//pipeline
