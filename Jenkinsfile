node{
    stage('Deploy to airflow'){
    sshagent(['tom']) {
    sh 'whoami'
    sh 'scp -o StrictHostKeyChecking=no /var/lib/jenkins/workspace/pipeline_anitha/*.py  ec2-user@3.84.230.74:/home/ec2-user/airflow/dags/'
    }
     sh 'pwd'
   //sh ' ssh -i /home/ec2-user/anithakey.pem  ec2-user@ec2-3.84.230.74.compute-1.amazonaws.com'
        sh 'cd'
        sh 'pwd'
 sh 'ssh -i /home/ec2-user/key/anithakey.pem ec2-3-84-230-74.compute-1.amazonaws.com -yes'
   
       sh 'pwd'
   
    sh 'whoami'
    dir("/home/ec2-user/airflow/") {
    sh 'pwd'
    //sh 'airflow webserver -p 8080 & airflow scheduler && fg'
}
    
        
    }
   
}  
