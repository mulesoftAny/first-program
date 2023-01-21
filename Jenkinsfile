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
            bat 'mvn clean deploy  -Dworkers=1 -Danypoint.username=ayanshko -Danypoint.password=Inthu@1234 -Dapplication.name=gitprogram -Denv=Sandbox -Dmule.version=4.4.0 -DmuleDeploy'
      }
    }
  }
}