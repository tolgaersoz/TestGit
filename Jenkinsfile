def workspace;
node
{
    stage('Checkout')
    {
        checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[credentialsId: '9f76879f-9b5f-4176-b322-eaaafae3c8f3', url: 'https://github.com/tolgaersoz/TestGit.git']]])
        workspace =pwd()
    }
    stage('Static Code Analysis')
    {
        echo "Static Code Analysis"
    }
    stage ('Code formatter Uncrustify')
    {
        bat '''cd uncrustify-0.66.1-win32
sleep 5
.\\uncrustify.exe -c .\\cfg\\defaults.cfg -f .\\Network.cpp  -o Networkfixed.cpp
'''

    }
    stage ('Build')
    {
        build 'TestGit'
    }
    stage ('Unit Testing')
    {
        echo "Unit Testing"
    }
    stage ('Delivery')
    {
        echo 'Deliver the code'
    }
    
}
