pipeline { 
  agent any 
  stages{
    stage('build artifacr'){
      steps{
        sh "mvn clean package -DskipTests=true"
        archive 'target/*.jar'
      }
    }
  }
} 
