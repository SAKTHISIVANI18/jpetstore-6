pipeline {

    agent any

    stages {

       
      stage('Package') {  
          steps{
    xldCreatePackage artifactsPath: 'build/libs', manifestPath: 'deployit-manifest.xml', warPath: 'jpetstore-1.0.3.0.war'  
  } 
      }
  stage('Publish') {  
      steps{
    xldPublishPackage serverCredentials: 'sakthi', warPath: 'jpetstore-1.0.3.0.war'
  }  
  }
  stage('Deploy') {  
      steps{
    xldDeploy serverCredentials: 'sakthi', environmentId: 'Environments/DEVS/sakthi', packageId: 'Applications/jpetstore/1.0.3.0'
  }  
  }
     
    }
}
