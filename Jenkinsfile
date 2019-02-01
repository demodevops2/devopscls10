node{
   stage('SCM Checkout'){
     git 'https://github.com/demodevops2/devopscls10'
   }
   stage('Compile-Package'){
      sh 'mvn clean package'
   }
  
      
    stage('Deploy to Tomcat'){ 
       
       sshagent(['tomcat-dev']) { 
          sh 'sudo scp -o StrictHostKeyChecking=no target/*.war 172.31.29.182:/var/lib/tomcat8/webapps/' 
       } 
    } 

    
}
