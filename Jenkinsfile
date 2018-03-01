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
}
post{
success{
gatlingArchive()
}
}
