node{
   stage('test'){
     git 'https://github.com/AnithaRamachandranR/jenkins'
     }
   stage('Deploy to airflow'){
    sshagent(['tom']) {
    sh 'scp -o StrictHostKeyChecking=no /var/lib/jenkins/workspace/anithapip/*.py  ec2-user@54.167.161.146:/home/ec2-user/airflow/dags/'

     }
    sh 'pwd'
    dir('ec2-user@54.167.161.146:/home/ec2-user/airflow'){
    sh 'pwd'
    }
     sh 'airflow webserver -p 8080 & airflow scheduler && fg '
    }
   
}  
