pipeline { 
  agent any 
  stages{
    stage('build artifacr'){
      steps{
        sh "mvn clean package -DskipTests=true" //test
        archive 'target/*.jar'
      }
    }
  }
}
