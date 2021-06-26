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
sh 'scp /home/ubuntu/.jenkins/workspace/MultibranchPipeline_main/webapp/target/webapp.war ubuntu@172.31.89.180:/var/lib/tomcat9/webapps/testapp.war'
    }
    stage('ContinuousTesting-master')
    {
        git 'https://github.com/intelliqittrainings/FunctionalTesting.git'
        sh 'java -jar /home/ubuntu/.jenkins/workspace/ScriptedPipeline/testing.jar'
    }
}    
