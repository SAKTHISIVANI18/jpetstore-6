pipeline {

    agent any

    stages {

       
      stage('Package') {  
          steps{
    xldCreatePackage artifactsPath: 'target/',manifestPath: 'deployit-manifest.xml', darPath: 'jpetstore-1.0.8.dar'  
  } 
      }
  stage('Publish') {  
      steps{
    xldPublishPackage serverCredentials: 'sakthi', darPath: 'jpetstore-1.0.8.dar'
  }  
  }
  stage('Deploy') {  
      steps{
    xldDeploy serverCredentials: 'sakthi', environmentId: 'Environments/DEVS/sakthi', packageId: 'Applications/jpetstore/1.0.8'
  }  
  }
     
    }
}
