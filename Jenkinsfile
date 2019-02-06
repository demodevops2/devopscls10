
node{
  stage('scm checkout'){
    git credentialsId: 'gitcreds', url: 'https://github.com/demodevops2/devopscls10.git'
  
  }
  stage('Build maven package'){
     sh 'mvn clean package'
  }
  
  stage('Deploy to Tomcat server'){ 
       
       sshagent(['tomcat-dev']) { 
          sh 'sudo scp -o StrictHostKeyChecking=no target/*.war 172.31.29.182:/var/lib/tomcat8/webapps/' 
       } 
    } 
}
