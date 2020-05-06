pipeline {

    agent any

    stages {

       
      stage('Package') {  
          steps{
    xldCreatePackage artifactsPath: 'libs-snapshot-local/', warPath: 'libs-snapshot-local/org/mybatis/jpetstore/6.0.3-SNAPSHOT/jpetstore-6.0.3-20200506.042637-9.war'  
  } 
      }
  stage('Publish') {  
      steps{
    xldPublishPackage serverCredentials: 'sakthi', warPath: 'libs-snapshot-local/org/mybatis/jpetstore/6.0.3-SNAPSHOT/jpetstore-6.0.3-20200506.042637-9.war'
  }  
  }
  stage('Deploy') {  
      steps{
    xldDeploy serverCredentials: 'sakthi', environmentId: 'Environments/DEVS/sakthi', packageId: 'Applications/jpetstore/1.0.3.'
  }  
  }
     
    }
}
