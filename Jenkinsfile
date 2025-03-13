pipeline { 
  agent any 
  stages{
    stage('build artifacr'){
      steps{
        sh "mvn clean package -DskipTests=true" //so that they can be downloaded later
        archive 'target/*.jar'
      }
    }
  }
}
