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
      stage('gatling') {
        steps{
        node {
            try {
                echo 'gatling archive'
            } finally {
                gatlingArchive()
            }
        }
        }
    }
}
