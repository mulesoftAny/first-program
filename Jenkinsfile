pipeline 
{
  agent any
  stages
  {
  	stage('prepare')
  	{
  	  steps
  	  {
  	  	configFileProvider([configFile(fileId:"88a727b0-f288-46a8-a289-043e5b2bdffc",targetLocation: 'env.groovy',variable: 'ENV')])
  	  	{
  	  		load "env.groovy";
  	  	}
  	  }
  	}
    stage('Build') 
    {
      steps
      {
            bat 'mvn clean install'
      }
    }
    stage('Deploy Development')
    {
    	environment
    	{
    		env="${APP_ENV}"
    		name="${APP_NAME}"
    		user="${ANYPOINT_USER}"
    		password=${ANYPOINT_PASSWORD}
    	}
      steps 
      {
            bat 'mvn clean deploy  -Dworkers=1 -Danypoint.username=%user% -Danypoint.password=%password% -Dapplication.name=%name% -Denv=%env% -Dmule.version=4.4.0 -DmuleDeploy'
      }
    }
  }
}