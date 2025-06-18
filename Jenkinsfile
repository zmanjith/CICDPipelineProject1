pipeline 
{
  agent { label 'NewNode'}
  tools {
    jdk 'java17'
    maven 'Maven3'  
  }
  stages {
   stage ("Cleanup Workspace" ) {
       steps {
         cleanWs()
       }
   }
    stage (" Checkout from SCM" ) {
      steps {
        git branch: 'main' , credentialsId: 'zmanjith', url: 'https://github.com/zmanjith/CICDPipelineProject1'
      }
    }
    stage ("Build Application") {
      steps {
        sh "mvn Clean Package"
      }
    }
    stage ("Test Application") {
      steps {
        sh "mvn test"
      }
      
    }
    
  }
}
