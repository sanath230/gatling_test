node()
{
cleanWs()
stage('clone')
{
checkout scm
}
stage('build')
{
sh "sbt gatling:test -Dgatling.simulationClass=computerdatabase.BasicItSimulation"
}
stage('post build')
  {
    post{
      always{
        gatlingArchive()
      }
    }
  }
}
