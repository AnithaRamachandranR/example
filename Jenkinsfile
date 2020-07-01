node{
   stage('SCM-CHECKOUT '){
     git 'https://github.com/AnithaRamachandranR/example'
     }
   stage('Compile-Package'){
      // Get maven home path
    def mvn_home = 'maven'
    withEnv( ["PATH+MAVEN=${tool mvn_home}/bin"] ) {
     sh "mvn clean install"
    }
   }
   stage('Deploy to Tomcat'){
      sshagent(['tom']) {
      sh 'scp -o StrictHostKeyChecking=no target/*.war  ec2-user@35.153.159.232:/home/ec2-user/tomcat/webapps/'
      }
  }
   
    stage('Deploy to airflow'){
    sshagent(['tom']) {
    sh 'whoami'
    sh 'scp -o StrictHostKeyChecking=no /var/lib/jenkins/workspace/pipeline_anitha/*.py  ec2-user@35.153.159.232:/home/ec2-user/airflow/dags/'
    sh 'ssh -i "anithakey.pem" ec2-user@ec2-35-153-159-232.compute-1.amazonaws.com'
       sh 'pwd'
   
    sh 'whoami'
    dir("/home/ec2-user/airflow/") {
    sh 'pwd'
    sh 'airflow webserver -p 8080 & airflow scheduler && fg'
}
    }
    }
   
}  
