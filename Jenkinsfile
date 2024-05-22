pipeline
{
    agent any
    stages
    {
        stage("contDownload")
        {
            steps
            {
                git branch: 'main', url: 'https://github.com/nocturnaldevops/NewProject24.git'
            }
        }
        stage("contBuild")
        {
            steps
            {
                sh 'mvn package'
            }
        }
    }
}