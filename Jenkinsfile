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
sh 'sbt gatling:test -Dgatling.simulationClass=BasicSimulation'
}
}  
stage('post build action')
{
steps
{ 
  node(){  
post{
success{
gatlingArchive()
}  
}
}  
}  
}
}
}  
