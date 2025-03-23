pipeline { 
  agent any 
  stages{
    stage('build artifact'){
      steps{
        sh "mvn clean package -DskipTests=true" //testt
        archive 'target/*.jar'
      }
    }
    stage('Unit tests - JUnit and Jacoco'){
      steps{
        sh "mvn test"
      }
      post {
        always{
          junit 'target/surefire-reports/*.xml'
          jacoco execPattern: 'target/jacoco.exec'
        }
      }
    }
    stage('Docker Build and Push') {
      steps {
          sh 'printenv'
          sh 'sudo docker build -t madebykatt/numeric-app:""$GIT_COMMIT"" .'
         sh 'docker push madebykatt/numeric-app:""$GIT_COMMIT""'
 
  }
} 
}
}
