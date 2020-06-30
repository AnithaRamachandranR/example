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
      sh 'scp -o StrictHostKeyChecking=no /var/lib/jenkins/workspace/pipeline_anitha/target/*.war  ec2-user@52.90.68.233:/home/ec2-user/tomcat7/webapps/'
      }
  }
   
    stage('Deploy to airflow'){
    sshagent(['tom']) {
    sh 'whoami'
    sh 'scp -o StrictHostKeyChecking=no /var/lib/jenkins/workspace/pipeline_anitha/*.py  ec2-user@52.90.68.233:/usr/local/airflow/dags/'
    sh 'pwd'
    sh 'whoami'
    dir("/home/ec2-user/airflow/") {
    sh 'pwd'
    sh 'airflow webserver -p 8080 & airflow scheduler && fg'
}
    }
    }
   
}  
