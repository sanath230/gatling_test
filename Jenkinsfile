pipeline
{
agent none
stages
{
stage('clean directory')
{
steps
{  
cleanWs()
}
}  
stage('clone')
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
sh "sbt gatling:test -Dgatling.simulationClass=computerdatabase.BasicItSimulation"
}
}  
stage('post build action')
{
steps
{  
post{
success{
gatlingArchive()
}
}  
}  
}
}
}  
