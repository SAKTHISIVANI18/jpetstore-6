pipeline {

    agent any

    stages {

        stage('checkout') {
            steps{
            sh 'https://github.com/SAKTHISIVANI18/jpetstore-6.git'
            }
        }

      stage('Package') {  
          steps{
    xldCreatePackage artifactsPath: 'build/libs', manifestPath: 'deployit-manifest.xml', darPath: 'jpetstore-1.0.3.0.dar'  
  } 
      }
  stage('Publish') {  
      steps{
    xldPublishPackage serverCredentials: 'sakthi', darPath: 'jpetstore-1.0.3.0.dar'
  }  
  }
  stage('Deploy') {  
      steps{
    xldDeploy serverCredentials: 'sakthi', environmentId: 'Environments/DEVS/sakthi', packageId: 'Applications/jpetstore/1.0.3.0'
  }  
  }
     
    }
}
