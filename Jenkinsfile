pipeline{
  agent any
  stages{
    stage("checkout"){
      steps{
           checkout([$class: 'GitSCM', branches: [[name: '*/master']], extensions: [], gitTool: 'achyuth501', userRemoteConfigs: [[credentialsId: 'achyuth', url: 'https://github.com/ammaladdine/build-deploy-project.git']]])
         }
       }
    stage("bulid"){ 
      steps{
          sh """
            mvn clean
            mvn install
          """
      }
    }
    stage("test"){ 
      steps{
          sh """
            mvn test
          """
      }
    }
    stage("pakage"){ 
      steps{
          sh """
            mvn pakage
          """
      }
    }  
  }
}
