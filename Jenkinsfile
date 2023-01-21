pipeline 
{
  agent any
  stages
  {
    stage('Build') 
    {
      steps
      {
            bat 'mvn clean install'
      }
    }
    stage('Deploy Development')
    {
      steps 
      {
            bat 'mvn clean deploy -DmuleDeploy'
      }
    }
  }
}