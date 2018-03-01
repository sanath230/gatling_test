pipeline
{
  agent none
    stages
    {
      stage('clone repo')
      {
        steps
        {
          checkout scm
        }
      }
      stage('build')
      {
        steps
        {
          sh 'sbt gatling:test -Dgatling.simulationClass=BasicSimulation'
        }
      }
      stage('post build')
      {
        steps
        {
          gatlingArchive()
        }
      }
    }
}
