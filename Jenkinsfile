pipeline{
  environment{
    reg = "sakshi1201/assignment10"
    regCre = "dockerid"
    dockerImg = ""
  }
  agent any
  stages{
    stage('Build Image'){
      steps{
        script{
          dockerImg = docker.build reg + ":$BUILD_NUMBER"
        }
      }
    }
    stage('Deploy the image'){
      steps{
        script{
          docker.withRegistry('',regCre){
            dockerImg.push()
          }
        }
      }
    }
  }
}
