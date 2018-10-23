def workspace;
node
{
    stage('Checkout')
    {
        checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[credentialsId: '9f76879f-9b5f-4176-b322-eaaafae3c8f3', url: 'https://github.com/tolgaersoz/TestGit.git']]])
        workspace =pwd()
    }
    stage ('Build')
    {
        build 'TestGit'
    }
    //stage('Code Analysis-Step1')
    //{
      //  echo "Static Code Analysis"
    //}
    stage ('Code Analysis-Step1')
    {
        dir('C:\\Program Files (x86)\\Jenkins\\workspace\\PipelineTest\\uncrustify-0.66.1-win32') {
    // some block
}
    }
    stage ('Code Analysis-Step2')
    {
        dir('C:\\Program Files (x86)\\Jenkins\\workspace\\PipelineTest\\uncrustify-0.66.1-win32') {
           powershell ' .\\uncrustifycheck.bat'
}
    }
    stage ('Unit Testing')
    {
        echo "Unit Testing"
    }
    stage ('Delivery')
    {
        echo 'Deliver the code'
    }
    stage ('Publish Report')
    {
        publishHTML([allowMissing: false, alwaysLinkToLastBuild: true, keepAll: true, reportDir: 'C:\\Program Files (x86)\\Jenkins\\jobs\\PipelineTest\\', reportFiles: 'index.html', reportName: 'HTML Report', reportTitles: 'Rapor'])
    }
    
}
