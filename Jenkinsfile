pipeline { 
  agent any 
  stages{
    stage('build artifact'){
      steps{
        sh "mvn clean package -DskipTests=true" //testt
        archive 'target/*.jar'
      }
    }
    stage('Unit tests'){
      steps{
        sh "mvn test"
      }
    }
  }
}
