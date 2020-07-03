node{
    stage('Deploy to airflow'){
    sshagent(['tom']) {
    sh 'whoami'
    sh 'scp -o StrictHostKeyChecking=no /var/lib/jenkins/workspace/pipeline_example/*.py  ec2-user@:54-80-110-214/home/ec2-user/airflow/dags/'
         sh " ssh ec2-user@54-80-110-214 'ls' "
    }
     sh 'pwd'
 //  sh ' ssh -i /home/ec2-user/anithakey.pem  ec2-user@54-80-110-214.compute-1.amazonaws.com'
       // sh 'cd ~'
        //sh 'pwd'
 //sh 'ssh -i /home/ec2-user/key/anithakey.pem ec2-54-80-110-214.compute-1.amazonaws.com -yes'
  
       sh 'pwd'
   
   // sh 'whoami'
//    dir("airflow/") {
  //  sh 'pwd'
   // sh 'airflow webserver -p 8080 & airflow scheduler && fg'
//}
    
        
    }
   
}  
