pipeline
{
agent none
stages
{
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
}
}  
node{
post{
success{
gatlingArchive() 
}
}  
}
