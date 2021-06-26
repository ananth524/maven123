node('master') 
{
    stage('ContinuousDownload-master')
    {
        git 'https://github.com/intelliqittrainings/maven.git'             
    }
    stage('ContinuousBuild-master')
    {
        sh 'mvn package'
    }
    stage('ContinuousDeployment-master')
   {
deploy adapters: [tomcat9(credentialsId: 'a120a0bc-3670-4590-9aae-ef0fd2fa0526', path: '', url: 'http://172.31.89.180:8080')], contextPath: 'testapp', war: '**/*.war'
            
    }
    stage('ContinuousTesting-master')
    {
        git 'https://github.com/intelliqittrainings/FunctionalTesting.git'
        sh 'java -jar /home/ubuntu/.jenkins/workspace/MultibranchPipeline_main/testing.jar'
    }
}    
