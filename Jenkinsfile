pipeline {
   agent any
   
   tools {
   
     maven 'Maven'
   }
   
   stages{
   
     stage('Checkpoint') {
     
           steps {
           
              git branch: 'main' , url: 'https://github.com/bitcsedevops195/AnsibleApp.git'
              
           }
      }
      
      
      stage('Build') {
     
           steps {
           
              sh 'mvn clean compile'
              
           }
      }
      
      
      stage('Archive') {
     
           steps {
           
              archiveArtifacts artifacts: 'target/*.war', fingerprint:true
              
           }
      }
      
      stage('Deploy') {
     
           steps {
           
              sh 'mvn clean compile'
              sh 'ansible-playbook ansible/playbook.yml -i ansible/hosts.ini'
              
           }
      }
      
   }
}
  
