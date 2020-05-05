pipeline {

    agent any

    stages {

       
      stage('Package') {  
          steps{
    xldCreatePackage artifactsPath: 'build/libs', warPath: '/var/lib/jenkins/workspace/jpetstore/target/JPetStore.war'  
  } 
      }
  stage('Publish') {  
      steps{
    xldPublishPackage serverCredentials: 'sakthi', warPath: '/var/lib/jenkins/workspace/jpetstore/target/JPetStore.war'
  }  
  }
  stage('Deploy') {  
      steps{
    xldDeploy serverCredentials: 'sakthi', environmentId: 'Environments/DEVS/sakthi', packageId: 'Applications/jpetstore/1.0.3.0'
  }  
  }
     
    }
}
