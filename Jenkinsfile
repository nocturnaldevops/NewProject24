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
                sh 'mvn packagee'
            }
        }
        stage("contDeploy")
        {
            steps
            {
                deploy adapters: [tomcat9(credentialsId: '84c9b9bd-7d19-4cd2-8bb7-d90477e63684', path: '', url: 'http://172.31.23.199:8080')], contextPath: 'test22', war: '**/*.war'
            }
        }
    }
}