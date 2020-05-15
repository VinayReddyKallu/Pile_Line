node
{
stage('checkout')
{
   checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[url: 'https://github.com/VinayReddyKallu/Pile_Line.git']]])
}
stage('Build')
{
    powershell 'javac HelloAll.java'
    powershell 'java HelloAll'
    powershell 'echo "The build number is ${env:BUILD_NUMBER}"'
    
}
stage('Test')
{
    echo "Testing.."

}
stage('Deploy')
{
    echo 'Deploy'
}
}
