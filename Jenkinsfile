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
   powershell 'jfrog rt c my_server --url=http://localhost:8081/artifactory --user=admin --password=vinay123'
   powershell 'jfrog rt u HelloAll.class FirstRepository/build_version_${env:BUILD_NUMBER}/'
}
}
