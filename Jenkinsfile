pipeline{
  agent any
  stages{
    stage("checkout"){
      steps{
           checkout([$class: 'GitSCM', branches: [[name: '*/master']], extensions: [], userRemoteConfigs: [[credentialsId: '5024bf71-1f54-484e-b916-e6850a05036e', url: 'https://github.com/ammaladdine/build-deploy-project.git']]])
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
    stage("package"){ 
      steps{
          sh """
            mvn package
          """
      }
    }  
  }
}
